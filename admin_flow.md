# Flow 管理

页面导航：

- [ 查询 Flow 信息 ](#flow_info)
- [ Flow 成员管理 ](#flow_members)（对 Flow 进行权限控制）
- [ 删除 Flow ](#flow_delete)

### <a name="flow_info">1、查询 Flow 信息</a>

图1：

<img src="https://images-cdn.shimo.im/l4Nlz2f06KkdLb0U/flow_info.jpg" style="zoom:30%">

如 <图1> 所示，Flow 列表中包含所有用户创建的 Flow，每个 Flow 有对应的 Webhook 地址 & Deploy Key，如仓库需要重新添加 Webhook，可在此出获取对应的 Webhook 添加到 Git 仓库。

### <a name="flow_members">2、Flow 成员管理</a>

图2：

<img src="https://images-cdn.shimo.im/u9icyGLX1WYRVPw4/flow_members.jpg" style="zoom:30%">

flow.ci 目前支持较粗粒度的权限控制，后续会细化权限控制系统，实现组权限以及自定义角色功能、支持 LADP，满足大型开发团队需求。

flow.ci 的权限控制是基于 flow 的，管理员可以为 flow 指定一个或多个成员，如 < 图2 > 所示，在 flow 成员管理界面中，我们为 test 分配了一个成员（ admin ）。

### <a name="flow_delete">3、删除 Flow</a>

在 flow 列表中找到你要删除的 flow，点击删除即可（注意：删除的 flow 不可恢复）。



<br/><br/><br/>

<div id="bom">
<a href="./admin_base.md">上一节：介绍 </a> |
<a href="./admin_flow.md">下一节：用户管理 </a>
</div>

<link rel="stylesheet" rev="stylesheet" href="flow.css" type="text/css"/> 