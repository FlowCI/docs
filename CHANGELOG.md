- v1.21.40 2021-10-05
  * 系统设置中可现实插件信息和同步状态
  * flow.ci python 包的问题修复
  * Bugfix

- v1.21.40 2021-10-05
  * Enable to show plugin and sync status from settings
  * Bugfix on flow.ci python lib
  * Bugfix on Agent

- v1.21.33 2021-08-18
  * 提升产品稳定性
  * Job 页面优化
  * 支持从变量中获取 Config 内容
  * Bugfix

- v1.21.33 2021-08-18
  * Stability improvement 
  * Job page improvement
  * Enable to load config content from the environment variable
  * Bugfix

- v0.21.21 2021-05-06
  * 新增 post step，在任务结束、失败或取消时执行
  * 可从失败的 step 从新开始任务
  * 支持从变量中获取 Secret
  * 改进 Agent 及任务的用户界面
  * BUG 修复

- v0.21.21 2021-05-06
  * Support post step that will be executed anyway
  * Enable to restart the job from failure step
  * Enable to get secret from the environment variable
  * UI improvement
  * Bugfix

- v0.21.05 2021-02-10
  * 支持并行任务
  * 支持任务缓存
  * 手动构建支持参数设置
  * 改进用户界面
  * BUG 修复

- v0.21.05 2021-02-10
  * Support parallel build
  * Support step level cache
  * Enable to modify parameters on manual build
  * UI improvement
  * Bugfix


- v0.20.45 2020-10-29
  * Agent 支持 Windows 环境
  * 支持 `bash` `pwsh`， 在任务中可自定义 Bash 或 PowerShell
  * 支持 `retry`, 可设置任务重试次数
  * 支持 `timeout`, 可以设置任务过期时间
  * 支持工作流级别的 condition，可以通过 Groovy 脚本自定义工作流启动规则
  * 新增 .Net Core 项目模板
  * BUG 修复

- v0.20.45 2020-10-29
  * Support Agent in Windows
  * Introduce `bash` `pwsh` in step level to define Bash and/or Powershell script
  * Introduce `retry` to defined retry times
  * Introduce `timeout` to defined timeout in seconds
  * Introduce `condition` in flow level to customize flow start condition with Groovy script
  * New template for .Net Core project
  * Bugfix

- v0.20.40 2020-10-01
  * 支持 k8s 中运行, 并动态扩展 Agent
  * PHP 构建模板
  * 支持定义子任务(sub-steps)
  * 新增管理员功能 - 系统配置
  * BUG 修复

- v0.20.40 2020-10-01
  * Support dynamic agents in a Kubernetes cluster.
  * PHP template
  * Support sub-steps in a step
  * New system configuration in the admin panel
  * Bugfix

- v0.20.32 2020-08-03
  * Web 用户界面优化
  * 可编辑 SSH 主机的端口
  * Web页面设置默认用户
  * 支持 `condition` YAML，可使用 Groovy 脚本来定义 Step 是否运行

- v0.20.32 2020-08-03
  * Improvement of UI
  * Enable to edit the port number on SSH host
  * Default user can be created from web
  * Support condition in the YAML to setup step start condition in Groovy

- v0.20.30 2020-07-27
  * Web 用户界面优化
  * 提升 Agent 的稳定性
  * 支持 flow 定时任务
  * 多容器的支持
  * 支持工作流级别的 `docker/dockers` YAML
  * 支持 `android` 秘钥类型，可以配置安卓签名
  * 新增安卓构建模板

- v0.20.30 2020-07-27
  * Improvement of UI
  * Improvement of Agent stability
  * Support crontab task for flow
  * Support multiple docker containers
  * Introduce `docker/dockers` YAML section on flow level
  * Introduce `android` secret type to config android certificate
  * New android flow template

- v0.20.26 2020-06-20
  * 支持在运行中的 Step 使用 Terminal 调试
  * 新增 'notification' YAML 配置通知插件
  * 新增 'token' 类型的 Secret
  * 可以在 Flow 设置页面配置 Job 过期时间
  * 支持显示 SSH RSA 公钥的 MD5 指纹
  * 新增 Sonarqube 插件
  * BUG 修复

- v0.20.26 2020-06-20
  * Support TTY on running step to debug
  * Introduce 'notification' YAML section to config flow notification task
  * Introduce 'token' secret type
  * Enable to config job timeout in flow settings
  * Support MD5 fingerprint on SSH RSA public key
  * New Sonarqube plugin
  * Important bugfix

- v0.20.20 2020-05-14
  * 支持任务 '重新开始'
  * 新增 ‘配置’ 功能
  * 添加了 npm 模板
  * 重要 BUG 修复

- v0.20.20 2020-05-14
  * Support 'rerun' for job
  * New configuration feature
  * Introduce an 'npm' build template
  * Important bugfix

- v0.20.16 2020-04-12
  * 支持 Gitee webhook
  * 可以从 Git 仓库中定义 YAML 配置 (.flowci.yaml)
  * 可以运行在 Docker 容器中运行 Step 和插件
  * 实时日志性能改进
  * Bugfix

- v0.20.16 2020-04-12
  * Support webhook for Gitee
  * Enable to load YAML configuration in Git repository (.flowci.yaml)
  * Enable to execute step and plugin in docker container
  * Impore performance on logging
  * Bugfix

- v0.20.09 2020-02-13
  * Job 详情页面支持图形显示，优化了 Log 终端的格式
  * 支持 Agent 通过 docker socket 的方式弹性伸缩
  * 支持 Agent 通过 ssh host 的方式弹性伸缩

- v0.20.09 2020-02-13
  * Optimize job detail page with step graphic view and log terminal layout
  * Support agent auto scaling via docker socket
  * Support agent auto scaling via ssh remote host

- v0.19.42 2019-12-06
  * 支持工作流统计
  * 支持 GitLab & Gogs webhook
  * 支持 HTML 报告页面 (Jacoco, Junit)
  * 支持 Agent 资源 (CPU, Memory) 显示
  * 优化 Job 页面
  * Bug fix
  
- v0.19.42 2019-12-06
  * Support flow job statistic view 
  * Support GitLab & Gogs webhook
  * Enable to show HTML report from plugin (Jacoco, Junit)
  * Enable to show Agent resource detail (CPU, Memory)
  * Optimize job detail page
  * Bug fix

- v0.1.4-alpha 2017-12-29
  * 支持 Web 定义工作流
  * 支持插件系统，以及插件-Agent同步
  * 支持 ‘final’ 节点，该节点为必执行节点
  * 支持 flow.ci 的 Windows 安装
  * 支持 Agent 通过 Cygwin 在 Windows 环境运行
  * bug fix
  
- v0.1.3-alpha 2017-12-08
  * 创建项目支持 oschina 仓库
  * yaml 工作流支持设置 condition，基于 Groovy 语法
  * bug fixed...https://github.com/orgs/FlowCI/projects/1（参见Done）
  
- v0.1.2-alpha 2017-12-01
  * yml 工作流支持设置工作目录    
  * yml 编辑器更新为 Monaco Editor
  * 轻松发布到 fir.im（基于 Docker）
  * 修复 bitbucket 无法正常克隆代码问题
