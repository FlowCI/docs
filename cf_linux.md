# 基于 Linux 的安装

最小运行环境:

- Java 8 (JRE or JDK)
- 至少 1 G 的内存
- 1 G 以上的空间

推荐运行环境: 

- Java 8 (JRE or JDK)
- 4 G 以上的内存
- 50 G 以上的空间

## 在 Debian 或者 Ubuntu 上安装

### 通过源码安装 Flow.ci 后台程序

##### 安装前的准备

**Java**

Flow.ci 是基于 Java 1.8 版本的应用程序，所以需要在机器上安装 Java 1.8 或以上的版本。如果不确定现有的 Java 版本，可以通过 `java -version` 命令检查当前的 Java 环境。

**Git**

Flow.ci 目前只支持基于 Git 的版本控制系统，所以需要在机器上安装 Git，可以通过 `git --version` 命令检查 Git 是否安装。

**Tomcat**

Tomcat 8.5 以上

**MySQL**

MySQL 5.6 以上
> 提示：确保 MySQL 的时区与服务器保持一致


##### 获取源码并编译

> 提示: Flow.ci 使用 maven 编译，3.0 以上版本， 可以在命令行中输入 `mvn -v` 检查 maven 是否正确安装。

  通过以下命令，编译所需要的 war / jar 包，结果输出在 ./dist 文件夹下

  ```bash
git clone -b master https://github.com/FlowCI/flow-platform.git
cd flow-platform
mvn clean package -DskipTests=true
ls ./dist
  ```

##### 配置 Flow.ci

1. 创建数据库

  Flow.ci 后端需要两个数据库对应不同的服务，可以执行以下语句在 MySQL 中创建所需要的数据库。

  ```sql
  mysql -u user_name -p -e "CREATE DATABASE flow_api_db CHARACTER SET utf8 COLLATE utf8_bin;"

  mysql -u user_name -p -e "CREATE DATABASE flow_cc_db CHARACTER SET utf8 COLLATE utf8_bin;"
```

2. 导入数据库

  ```sql
  mysql -u user_name -p --database=flow_api_db < flow-platform/schema/flow_api_db.sql

  mysql -u user_name -p --database=flow_cc_db < flow-platform/schema/flow_cc_db.sql
```

3. 更改及设置配置文件

  **app-api.properties**

   ```properties
   ### JDBC config ###
   jdbc.url = jdbc:mysql://127.0.0.1:3306/flow_api_db?useSSL=false
   jdbc.username = db_username
   jdbc.password = db_password
   jdbc.pool.size = 50
   jdbc.commit.auto = false
   jdbc.connection.timeout = 20000

   ### Hibernate config ###
   hibernate.show_sql = false
   hibernate.hbm2ddl.auto = validate

   ### api settings ###
   api.workspace = ${HOME}/flow-api-data
   api.zone.default = default
   api.user.expire = 86400000

   ### domain ###
   domain.api = http://localhost:8080
   domain.web = http://localhost:3000
   domain.cc = http://localhost:8080

   task.job.toggle.execution_timeout = false
   ## 600s expire job
   task.job.toggle.execution_create_session_duration = 600
   ## 1h expire job
   task.job.toggle.execution_running_duration = 3600
   ```
   
   **app-cc.properties**
   
  ```properties
  ### jdbc config ###
  jdbc.url = jdbc:mysql://127.0.0.1:3306/flow_cc_db?useSSL=false
  jdbc.username = db_username
jdbc.password = db_password
jdbc.pool.size = 50
jdbc.commit.auto = false
jdbc.connection.timeout = 20000

  ### hibernate config ###
hibernate.show_sql = false
hibernate.hbm2ddl.auto = validate

  ### zookeeper config ###
zk.server.embedded = true
zk.host = 127.0.0.1:2181
zk.timeout = 30
zk.node.root = flow-agents

  # zone names and cloud provider config, ex: a=xxx;b=xxx;c=xxx
zk.node.zone = default
zone.default.agent_session_timeout = 600
zone.default.default_cmd_timeout = 600

  ### rabbitmq config ###
mq.host = amqp://localhost:5672
mq.management.host = http://localhost:15672

  #### cmd queue settings ###
queue.cmd.retry.enable = false
queue.cmd.rabbit.enable = false
queue.cmd.rabbit.name = flow-cmd-queue-default
queue.cmd.idle_agent.timeout = 30
queue.cmd.idle_agent.period = 5

  ### agent config ###
agent.config.ws = ws://localhost:8088
agent.config.cc = http://localhost:8080

  ### task toggles ###
task.zone.toggle.keep_idle_agent = false
task.agent.toggle.session_timeout = true
task.cmd.toggle.execution_timeout = true
task.instance.mos.toggle.clean = true
   ```

  > 根据用户所设置信息，需要修改 API 配置文件中的 MySQL 设置， 以及对应的 domain 地址的设置。更详细的配置文件说明，请参见 <a>配置文件说明</a>

##### 导入配置文件并启动
 
安装 dist 目录下的 flow-api-*.war 以及 flow-control-center-*.war 到 Apache Tomcat 服务器中，并设置上一步配置的 `app-api.properties` 到 `FLOW_API_CONFIG_PATH` 环境变量，`app-cc.properties` 到 `FLOW_CC_CONFIG_PATH` 环境变量。

启动 Apache Tomcat 后，可通过在浏览器中键入 `所配置的路径/index ` 地址，验证服务是否启动成功。

> 例如: 所配置的网址为: http://yourhost.com
> 两个服务在 Tomcat 中配置的路径分别为 `flow-api`， `flow-control-center`，则在浏览器中输入 http://yourhost.com/flow-api/index 验证主 API 服务是否启动成功，输入 http://yourhost.com/flow-control-center/index 验证控制中心的服务是否启动成功。


### 通过源码安装 Flow.ci web 页面

Flow.ci 采用的为前后端分离的结构，所以需要用户在安装后台服务后，安装 web 界面。

#### 安装前的准备

**node.js**

Node.js v6.6.0 以上版本

**npm**

npm v3 以上版本


##### 获取源码并编译

通过以下脚本编译 web 项目，编译成功后，请在 dist 文件夹下查看编译好的项目文件。

> 请根据配置的 API URL 替换 `FLOW_WEB_API` 环境变量。

```bash
git clone -b master https://github.com/FlowCI/flow-web.git
cd flow-web
export NODE_ENV=production
export FLOW_WEB_API="http://your_flow_api_url"
npm run compile
```

##### 部署

web 可以部署在任意 http 应用服务器上，如 Nginx, Apache Http Server 等。
> 提示: web 项目使用 react 构建，需要在部署到 http 应用服务器后，配置服务器的路由，否则会无法刷新页面。如在 Nginx 上，需添加配置 `try_files $uri /index.html;`