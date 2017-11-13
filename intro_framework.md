# flowci 整体架构

flowci 主要分为三个部分，如下图所示:

<img src="https://images-cdn.shimo.im/GoWZdCbi1OwuSdRR/image.png!thumbnail" style="zoom:30%">

**flow Front End:**

flowci 的前端部分，现阶段主要为 web 页面。

> 后期会提供命令行工具，IDE 插件等

**flow API:**

此服务主要提供 flowci 的基础服务，如 flow 管理，job 管理，用户管理等。


**flow Control Center:**

flowci  Agent 控制中心（简称 CC），主要包括控制 Agent 状态，命令分发，Agent 配置管理等功能。


<br/><br/><br/>

<div id="bom">
<a href="./intro_base.md">上一节：flowci 简介 </a> |
<a href="./cf_linux.md">下一节：基于 Linux 的安装 </a>
</div>

<link rel="stylesheet" rev="stylesheet" href="flow.css" type="text/css"/> 