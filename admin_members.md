# flow.ci 成员管理

页面导航：

- [ flowci 角色说明 ](#role_info)
- [ 添加成员 ](#member_add)
- [ 查询成员信息 ](#member_info)
- [ 成员角色变更 ](#member_auth)
- [ 删除成员 ](#member_delete)

### <a name="role_info">1、flowci 角色说明</a>

flowci 目前包含两种角色：Admin & User

Admin  角色拥有 “flowci 控制台管理权限”，同时拥有 User 权限。

User 角色拥有 “新建 flow 以及 flow 构建权限”。

### <a name="member_add">2、添加成员</a>

图1

<img src="https://images-cdn.shimo.im/TewNxF46bzANXkfl/memberinfo.jpg" style="zoom:30%">

添加成员默认分配角色为 User，可在创建时给成员进行 flow 授权，授权后该成员即拥有 flow 的操控权。

如勾选 “发送账户详情电子邮件”，添加成员成功后，该成员邮箱会收到一封账户信息邮件，包含用户名 & 初始密码。


### <a name="member_info">3、查询成员信息</a>

如  <图1> ，切换到成员列表，即可查看所有成员以及成员信息。

### <a name="member_auth">4、成员角色变更</a>

图2

<img src="https://images-cdn.shimo.im/bC9nr8iNLFc2fvww/member_auth.jpg" style="zoom:30%">

如 <图2>，在成员列表中勾选某个成员，在下拉菜单中选择要变更后的角色，点击应用即可完成角色变更。

### <a name="member_delete">5、删除成员</a>

在成员列表中勾选某个成员，点击删除。


<br/><br/><br/>

<div id="bom">
<a href="./admin_flow.md">上一节：flow 管理 </a> |
<a href="./admin_plugin.md">下一节：插件管理 </a>
</div>

<link rel="stylesheet" rev="stylesheet" href="flow.css" type="text/css"/> 