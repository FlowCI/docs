* [什么是 flow.ci](cn/)

* 快速开始
  * [安装](cn/start/index.md#安装)
  * [配置 URL](cn/start/index.md#配置服务器URL)
  * [创建工作流](cn/start/index.md#创建工作流)
  * [开始任务](cn/start/index.md#开始任务)

* 工作流 (flow)
  * [结构](cn/flow/structure.md)

* 任务 (job)
  * [开始](cn/job/start.md)
  * [工作区](cn/job/workspace.md)
  * [运行条件](cn/job/condition.md)
  * [通过 Docker 配置运行环境](cn/job/docker.md)
  * [并行执行](cn/job/parallel.md)
  * [缓存](cn/job/cache.md)
  * [定时任务](cn/job/schedule.md)
  * [网页终端](cn/job/web_terminal.md)

* Git 仓库
  * [工作流中配置 Git](cn/git/index.md)
  * [连接 Github](cn/git/github.md)
  * [连接 Gitlab](cn/git/gitlab.md)
  * [连接 Gogs](cn/git/gogs.md)
  * [连接 Gitee](cn/git/gitee.md)

* Agent
  * [什么是 Agent](cn/agents/index.md)
  * [添加 Agent](cn/agents/manual.md)
  * 弹性伸缩
    * [Kubernates](cn/agents/k8s_host.md)
    * [SSH 主机](cn/agents/ssh_host.md)

* 密钥 (Secret)
  * [SSH-RSA](cn/secret/ssh-rsa.md)
  * [用户名密码](cn/secret/auth.md)
  * [Token](cn/secret/token.md)
  * [安卓签名](cn/secret/android_sign.md)
  * [K8s kubeconfig](cn/secret/kubeconfig.md)


* 通用配置 (Config)
  * [SMTP](cn/config/smtp.md)
  * [任意配置(text)](cn/config/freetext.md)

* 触发器 (Trigger)
  * [任务结束事件](cn/trigger/on_job_finish.md)
    - [发送邮件](cn/trigger/on_job_finish.md#发送邮件)
    - [发送 HTTP 请求](cn/trigger/on_job_finish.md#发送-http-请求)

* 插件 (Plugins)

* 参考
  * [YAML](cn/yml/reference_v1.md)
  * [环境变量](cn/agents/vars.md)