# 消息通知

页面导航：

- [ 邮件设置 ](#msg_mail)
- [ 钉钉设置 ](#msg_dingding)

Flow.ci 支持将 “构建失败、成功或其它自定义消息” 发送到邮箱、钉钉等，在此处配置邮件服务器或钉钉机器人。

### <a name="msg_mail">1、邮件设置</a>

图1

<img src="https://images-cdn.shimo.im/zUUwdX9Xu4cABFde/msg_mail.jpg" style="zoom:30%">

如 <图1> ，目前 Flow.ci 发送邮件只提供 SMTP 模式，配置前请检查您所使用邮箱是否开启 SMTP。

填写相关配置信息后，点击 “测试发送” 测试配置是否正确，之后保存配置。

如何获取邮箱 SMTP 相关信息？（ sohu 邮箱举例 ）

在 sohu 邮箱设置中，找到 “邮件服务”，选择 “POP3/SMTP/IMAP”，在设置中开启 “SMTP” 服务，“提示” 一栏即可看看到邮箱 SMTP 服务地址。SMTP 的默认端口为 “25”。之后在 Flow.ci 控制台填写该信息即可。

<img src="https://images-cdn.shimo.im/J5lWUzOe3SYDcnJA/sohu_smtp.jpg" style="zoom:30%">

### <a name="msg_dingding">2、钉钉设置</a>

coming soon...

<br/><br/><br/>

<div id="bom">
<a href="./admin_credentials.md">上一节：证书管理 </a> |
<a href="./admin_system_info.md">下一节：系统信息 </a>
</div>

<link rel="stylesheet" rev="stylesheet" href="flow.css" type="text/css"/> 

