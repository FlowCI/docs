# 如何找到 Provisioning Profiles & 证书文件

### Provisioning Profiles

你可以直接在苹果开发者后台下载 Provisioning Profiles，点击 [ 去苹果开发者后台下载 ](https://developer.apple.com/account/ios/profile/profileList.action)。

### 签名证书

打开钥匙串访问，点击证书，选择证书文件

<img src="https://images-cdn.shimo.im/TbH4Lk3jNOoaLpKJ/ios_p12.png" style="zoom:80%">

同时选择证书和专用密钥两项，右键导入专用2项

<img src="https://images-cdn.shimo.im/ZK0N2DDzez0AT4XI/ios_p12_2.png" style="zoom:80%">

导出证书，并设置证书密码

<img src="https://images-cdn.shimo.im/GiCOBE6jGNk0gNoY/ios_p12_3.png" style="zoom:80%">


**之后将 P12 证书文件  & Provisioning Profiles 文件双击安装到 Agent 机器上即可。**


<br/><br/><br/>

<div id="bom">
<a href="./other_ci_devops.md">上一节：CI 与 DevOps 的关系 </a> |
<a href="./admin_base.md">下一节：管理员文档-简介 </a>
</div>

<link rel="stylesheet" rev="stylesheet" href="flow.css" type="text/css"/> 

