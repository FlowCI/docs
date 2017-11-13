# 证书管理

页面导航：

- [ 添加证书 ](#credential_add)
- [ 查询证书 ](#credential_info)

flowci 目前证书（Credentials
）类型有两种，一种是仓库授权需要使用的 SSH RSA 证书，另外一种是构建 iOS 项目时使用的 iOS 开发证书（.P12）和描述文件（.mobileprovision）。

### <a name="credential_add">1、添加证书</a>

- 添加 RSA 证书

在控制台中选择 “添加 Credential” ，证书类型选择 “RSA”，填写证书名称之后即可生成 RSA 证书，在列表中复制证书内容添加到目标机器即可。

- 添加 iOS 证书

在控制台中选择 “添加 Credential” ，证书类型选择 “iOS 证书”，上传 iOS 开发证书（.P12）和描述文件（.mobileprovision）即可。

### <a name="credential_info">2、查询证书</a>

图1

<img src="https://images-cdn.shimo.im/63Rw6GKlOCIHo1if/credential_list.jpg" style="zoom:30%">

如 <图1> ，在 “Credential 列表” 中选择要查询的证书类型即可查询证书相关信息。




<br/><br/><br/>

<div id="bom">
<a href="./admin_agent.md">上一节：Agent 管理 </a> |
<a href="./admin_msg.md">下一节：消息通知 </a>
</div>

<link rel="stylesheet" rev="stylesheet" href="flow.css" type="text/css"/> 


