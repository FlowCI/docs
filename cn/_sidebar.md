* [什么是 flow.ci](cn/)

* 快速开始
  * [安装](cn/start/index.md#安装)
  * [配置服务器 URL](cn/start/index.md#配置服务器URL)
  * [创建工作流](cn/start/index.md#创建工作流)
  * [开始任务](cn/start/index.md#开始任务)

* 工作流 (flow)
  * [结构](cn/flow/structure.md)

* 任务 (job)
  * [开始任务](cn/job/start.md)
  * [运行条件](cn/job/condition.md)
  * [运行环境](cn/job/environment.md)
  * [并行执行](cn/job/parallel.md)
  * [定时任务](cn/job/schedule.md)
  * [Web Terminal](cn/job/web_terminal.md)

* Git 仓库
  * [工作流中配置 Git](cn/git/index.md)
  * [连接 Github](cn/git/github.md)
  * [连接 Gitlab](cn/git/gitlab.md)
  * [连接 Gogs](cn/git/gogs.md)
  * [连接 Gitee](cn/git/gitee.md)

* Agents
  * [手动配置](cn/agents/manual.md)
  * 弹性伸缩
    * [配置 SSH 主机](cn/agents/ssh_host.md)
    * [配置 K8s](cn/agents/k8s_host.md)

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
    - [Email 触发器](cn/trigger/on_job_finish.md#配置-email-触发器)
    - [Webhook 触发器](cn/trigger/on_job_finish.md#配置-webhook-触发器)

* 插件 (Plugins)

* 参考
  * [YAML](cn/yml/reference_v1.md)
  * [环境变量](cn/agents/vars.md)