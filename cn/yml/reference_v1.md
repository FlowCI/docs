# YAML 参考

* [`envs`](#envs)
* [`trigger`](#trigger)
* [`selector`](#selector)
* [`docker` / `dockers`](#docker/dockers)
  * `image`
  * `ports`
  * `user`
  * `entrypoint`
  * `command`
  * `environment`
  * `network`
  * `is_runtime`
  * `stop_on_finish`
  * `delete_on_finish`
* [`notifications`](#notifications)
  * `plugin`
  * `envs`
* [`steps`](#steps)
  * [`name`](#name)
  * [`condition`](#condition)
  * [`allow_failure`](#allow_failure)
  * [`envs`](#envs)
  * [`script`](#script)
  * [`docker` / `dockers`](#docker/dockers)
    * `image`
    * `ports`
    * `user`
    * `entrypoint`
    * `command`
    * `environment`
    * `network`
    * `is_runtime`
    * `stop_on_finish`
    * `delete_on_finish`
  * [`plugin`](#plugin)
  * [`exports`](#exports)

-----------

## envs

全局环境变量，可以在所有的 Step 中使用

```yaml
envs:
  FIRST_ENV: "first var"
  SECOND_ENV: "hello world"
```

## trigger

当 Git 仓库推送 Push，Tag，或者 Pull Request 等事件时，可以根据 `branch` 或者 `tag` 来觉得是否执行工作流。
  
```yaml
trigger:
  branch:
    - "develop"
    - "master"
    - "feature/*"
  tag:
    - "*"
```

## selector

`selector` 可以根据 Agent 的 Tag 来决定当前工作流运行在哪个 Agent 上运行，如果该配置为空，则当前工作流可以运行在所有的 Agent 上。

```yaml
selector:
  label:
    - ios
    - local
```

## docker/dockers

当配置 `docker` 或者 `dockers` 时，说明当前工作流的所有 Step 将运行在容器中。

### 配置 Docker (`docker`)

```yml
docker:
  image: ubuntu:18.04 # 必填项
  ports: # 可选
  - "8080:8080"
  - "9090:9090"
  user: root # 可选, 默认为 root
  entrypoint: # 可选, 默认为 "/bin/bash"
  - "/bin/bash"
  stop_on_finish: 'true' # 可选, 默认为 true
  delete_on_finish: 'ture' # 可选, 默认为 true

steps:
- name: step name
  allow_failure: true
  envs:
    MY_ENV: "hello"
  script: |
    echo $MY_ENV
```

### 配置多个 Docker (`dockers`)

例如下面的配置，每个 Step 运行时启动 3 个容器 (Image 分别为 ubuntu:18.04, mysql:5.6, rabbitmq:3)， 其中 ubuntu:18.04 为 Step 的运行环境.

```yml
dockers:
- image: ubuntu:18.04
  entrypoint: ["/bin/bash"] # 可选, 默认为 /bin/bash
  is_runtime: true # # 可选, 默认为列表中的第一个为 Step 的运行环境

- image: mysql:5.6
  environment: # 可选, 可以配置容器的环境变量
    MYSQL_ROOT_PASSWORD: my_password
  ports: # 可选
  - "3306:3306"
  user: root # 可选, 默认为 root
  entrypoint: [] # 可选, 默认为空
  command: [] # 可选, 默认为空
  network_mode: "bridge" # 可选, 默认为 bridge
  stop_on_finish: 'true' # 可选, 默认为 true
  delete_on_finish: 'ture' # 可选, 默认为 true

- image: rabbitmq:3

steps:
- name: step name
  allow_failure: true
  envs:
    MY_ENV: "hello"
  script: |
    echo $MY_ENV
```

## notifications

消息通知配置，可以使用消息通知类型的插件，当任务结束后发送通知。

```yaml
notifications:
  - plugin: 'email-notify'
    envs:
      FLOWCI_SMTP_CONFIG: 'test-config'
```

## steps

#### name

可以自定义 Step 的名称，默认值为 step-1, step-2, step-xx

```yml
steps:
- name: step name
```

#### condition

可以定义一个返回值为布尔的 Groovy 脚本，确定该 Step 可否运行

```yml
steps:
- name: step name
  envs:
    my_var: "hello"
  conditon: |
    ## groovy script that return boolean value
    return "$my_var" == "hello";
```

#### allow_failure

允许失败，如果该值为 `true`，则表示 Step 失败后可继续运行后面的 Step。默认值为 `false`

```yml
steps:
- name: step name
  allow_failure: true
```

#### envs

Step 级别的环境变量 （优先级高于工作流级别）

```yml
steps:
- name: step name
  allow_failure: true
  envs:
   MY_ENV: "hello"
```

#### script

要执行的 bash 脚本

```yml
steps:
- name: step name
  allow_failure: true
  envs:
    MY_ENV: "hello"
  script: |
    echo $MY_ENV
```

#### docker/dockers

Step 级别的设置（优先级高于工作流级别），具体配置请参考工作流的 [`docker` / `dockers`](#docker/dockers) 配置

#### plugin

在 Step 中应用插件，

> 当插件应用后， `script` 为可选项, 如果 `script` 定义了脚本，则会在插件执行前执行。

```yml
steps:
- name: run unit test
  envs:
    ENV_FOR_PLUGIN: "xxx"
  plugin: 'maven-test' # the plugin name
```

#### exports

输出环境变量，所输出的环境变量可以在之后的 Step 中使用。

```yml
steps:
- name: step name
  script: |
    echo $MY_ENV
    export ENV_FOR_NEXT_STEP="hello"
  exports:
  - "ENV_FOR_NEXT_STEP"
```
