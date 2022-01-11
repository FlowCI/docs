<h3 align="center">
  <a href="https://flowci.github.io">
    <img src="https://github.com/FlowCI/docs/raw/master/src/logo.png" alt="Logo" width="100">
  </a>
</h3>

<h3 align="center">A Simple & Powerful CI/CD Server</h3>

<p align="center">
    <a href="https://github.com/FlowCI/docs/blob/master/LICENSE"><img src="https://img.shields.io/github/license/flowci/flow-core-x"></a>
    <a href="https://github.com/FlowCI/flow-core-x/releases/"><img src="https://img.shields.io/github/v/release/flowci/flow-core-x"></a>
    <a href="https://github.com/FlowCI"><img alt="GitHub Org's stars" src="https://img.shields.io/github/stars/flowci"></a>
    <a href="https://hub.docker.com/u/flowci"><img alt="Docker Pulls" src="https://img.shields.io/docker/pulls/flowci/core"></a>
</p>

<div align="center">

**[English](en/README.md) | 简体中文**

</div>

## 什么是 flow.ci

flow.ci 是一款开源的持续集成服务，与其他的持续集成服务相比，能够开箱即用，简化了繁琐的配置，并增加了用户体验。

- __高可用__

    flow.ci 采用前后端分离架构，可工作在任何环境中，支持多个前后端事例部署，保证在节点宕机情况下任务不会丢失。

- __构建速度__

    - __自动伸缩__: 在 k8s 或者 linux 中运行的 Agent 可以根据需要自动伸缩
    - __并行任务__: 任务中的每个步骤都可以在不同的 Agent 上并行执行，可极大的提高构建速度
    - __缓存__: 支持任务缓存，省去下载时间

- __开箱即用__

    只需一行命令即可安装 flow.ci 服务，可根据提供的模版创建工作流，修改仓库后即可开始任务。

- __在线调试__
    
    flow.ci 可以在任务运行时在线进入终端，进行调试

- __灵活的插件__

    flow.ci 的插件可以用任意语言编写。使用插件也非常简单，只需要在 `YAML` 中配置插件名称即可

- __灵活的环境支持__ 
  
    任务中的每个步骤都可以指定 docker 镜像，在任意的环境中执行

## 快速开始

> 需要安装 [Docker](https://docs.docker.com/install/) & [Docker-Compose](https://docs.docker.com/compose/install/)

```bash
git clone https://github.com/FlowCI/docker.git flow-docker
cd flow-docker
./server.sh start
```

## 文档

+ [简体中文](https://github.com/FlowCI/docs/tree/master/cn/index.md)

如果需要帮助? 从[这里]提交问题 (https://github.com/FlowCI/docs/issues) 或发送邮件至 `flowci@foxmail.com`


## 构建模板

[maven, npm, golang, ruby, android and more](https://github.com/FlowCI/templates)


## 基本架构

![architecture](https://github.com/FlowCI/docs/raw/master/src/architecture.png)

## 预览

![demo](https://github.com/FlowCI/docs/raw/master/src/demo.gif)
