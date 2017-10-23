# FAQ

###  <a name="add_webhook">如何添加 webhook 地址到你的 Git 仓库？</a>

在 GitHub 中打开你的项目，然后依次点击 “Settings” - “Webhooks” - “Add webhook”。

图3

<img src="https://images-cdn.shimo.im/ik4ER7hszvw2b0NZ/addwebhook.jpg" style="zoom:30%">

在 “Payload URL” 中输入 webhook 地址，并选择 “Content type” 为 application/json。

推荐修改触发 webhook 的事件为 Push & PullRequest，不使用默认的 “Send me everything”。

最后点击 “Add webhook” 按钮完成创建 Webhook。




<br/><br/><br/>

<div id="bom">
<a href="./">上一节：最佳实践 </a> |
<a href="./other_cooperate.md">下一节：参与协作 Flow.ci </a>
</div>

<link rel="stylesheet" rev="stylesheet" href="flow.css" type="text/css"/> 