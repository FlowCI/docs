- v0.20.09 2020-02-13
  * Job 详情页面支持图形显示，优化了 Log 终端的格式
  * 支持 Agent 通过 docker socket 的方式弹性伸缩
  * 支持 Agent 通过 ssh host 的方式弹性

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
