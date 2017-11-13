# Agent 管理

页面导航：

- [ 新建 Agent ](#agent_add)
- [ 启动 Agent ](#agent_start)
- [ 查询 Agent 状态 & 当前任务 ](#agent_info)
- [ Agent 操作 ](#agent_operate)

**Agent 名词解释**：Agent 是 flowci 中负责执行构建任务的最基本单元，一台物理机可以启动多个 Agent。

### <a name="agent_add">1、新建 Agent</a>

在控制台中选择 “添加 Agent”，填写 Agent 名称后生成 Agent。

在 Agent 列表中可获取新创建 Agent 的相关信息（例如 Agent Token）。

### <a name="agent_start">2、启动 Agent</a>

进入 Agent 所在目录，执行以下命令启动 Agent：

```·
命令 & 参数：
java -jar [ Agent 文件名 ] [ API 地址 ] [ Agent Token ]

举例：
java -jar flow-agent-0.0.1.jar http://127.0.0.1:8080/flow-api 71b33e03-86e2-452c-85af-da23a28b452a
```

### <a name="agent_info">3、查询 Agent 状态 & 当前任务</a>

Agent 列表中会标识出每个 Agent 的运行状态，运行状态有三种，分别是：“关机”、“无任务”、“正在构建”。

### <a name="agent_operate">4、Agent 操作</a>

- 停止任务：点击 “停止任务” 按钮，会停止 Agent 正在构建的任务。
- 删除 Agent：点击 “删除” 按钮，会在 Agent  当前任务构建完成后，删除 Agent 实例。


<br/><br/><br/>

<div id="bom">
<a href="./admin_plugin.md">上一节：插件管理 </a> |
<a href="./admin_credentials.md">下一节：证书管理 </a>
</div>

<link rel="stylesheet" rev="stylesheet" href="flow.css" type="text/css"/> 