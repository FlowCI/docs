# 主要功能

flow.ci 是开源的 CI/CD 工具，让用户在更轻松，友好的环境下进行持续集成/部署，对于其他的 CI/CD `jenkins`, `gocd`, `teamcity` 等工具，flow.ci 具有如下特点:

- 简单、友好: 根据模板创建项目， 分分钟即可开始一次构建

- Agent 可根据需要自动伸缩，加快构建速度

- 支持负载均衡

- 更简单易懂的 YAML 配置，不用查看文档即可修改

- 多环境支持，任务可以运行在大多数 Docker 镜像中，可以运行 java, python, go, ruby 等任何语言的任务

- 灵活的插件系统，可以让配置更简单

- CI 中出现奇怪的问题？可以使用 web terminal 在线进行调试

望各位顺手 star 以示支持, 感谢！

# 目录

* 快速开始
  * [开始第一次构建](./start/index.md)

* [与 Git 仓库建立连接](./git/index.md)
  * [Github](./git/github.md)
  * [Gitlab](./git/gitlab.md)
  * [Gogs](./git/gogs.md)
  * [Gitee](./git/gitee.md)

* YAML 配置
  * [参考](./yml/reference_v1.md)
  * [插件](./yml/plugins.md)
  * [模板](https://github.com/FlowCI/templates)

* Agents
  * 手动配置
    * [Linux](./agents/manual.md)
    * [MacOS](./agents/manual.md)
    * [Windows](./agents/manual.md)
    * [Docker](./agents/manual.md)
  * 自动配置
    * [配置 SSH 主机](./agents/ssh_host.md)
    * [配置 K8s](./agents/k8s_host.md)
  * [默认的环境变量](./agents/vars.md)

* Secret
  * [SSH-RSA](./secret/ssh-rsa.md)
  * [用户名密码验证](./secret/auth.md)
  * [Token](./secret/token.md)
  * [安卓签名](./secret/android_sign.md)
