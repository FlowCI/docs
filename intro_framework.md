# Flow.ci 整体架构

Flow.ci 主要分为三个部分，如下图所示:

<img src="https://images-cdn.shimo.im/GoWZdCbi1OwuSdRR/image.png!thumbnail" style="zoom:30%">

**Flow Front End:**

Flow.ci 的前端部分，现阶段主要为 web 页面。

> 后期会提供命令行工具，IDE 插件等

**Flow API:**

此服务主要提供 Flow.ci 的基础服务，如 Flow 管理，Job 管理，用户管理等。


**Flow Control Center:**

Flow.ci  Agent 控制中心（简称 CC），主要包括控制 Agent 状态，命令分发，Agent 配置管理等功能。