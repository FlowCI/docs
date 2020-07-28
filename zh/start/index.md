# 开始使用 flow.ci

## 1. 安装

> 需要预先安装 [Docker](https://docs.docker.com/install/) & [Docker-Compose](https://docs.docker.com/compose/install/)

安装 flow.ci 只需要运行如下脚本:

```bash
git clone https://github.com/FlowCI/docker.git flow-docker
cd flow-docker
./server.sh start
```

等待完成后，可通过浏览器访问 `http://localhost:2015`, 使用默认的用户名 `admin@flow.ci` 和密码 `example` 登录.

![cmd](../../src/start_server.gif)

## 2. 创建工作流

- 输入工作流名称
  - 点击 '创建工作流'
  - 按提示输入工作流名称
  
- 选择 YAML 配置模板

## 3. 开始第一次任务

点击 `运行` 开始任务

> - 如果选择空模板，则需要配置 YAML 后才可以开始任务
> - 如何配置 Git 仓库，请参考 [Git 仓库配置](../git/index.md)

![start](../../src/create_flow_and_build.gif)
