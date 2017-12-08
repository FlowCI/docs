# iOS 项目构建

页面导航：

- [ 环境准备 ](#ios_build_envir)
- [ 创建 flow ](#ios_create_flow)
  - [ 配置 Git 仓库 ](#git_config)
  - [ 配置 yml 工作流 ](#yml_config)
- [ 触发构建 ](#ios_build_trigger)
- [ 获取产物 ](#ios_get_ipa)

### <a name="ios_build_envir">1、环境准备</a>

* 安装 Fastlane

 - 目前 flow.ci 尚处于 alpha 版本，没有完全集成 fastlane，需要用户手动在 Agent 机器上安装 fastlane，参见：https://docs.fastlane.tools/getting-started/ios/setup/

* 导入证书

 - 参见：[如何找到 Provisioning Profiles & 证书文件](./other_p12.md)

### <a name="ios_create_flow">2、创建 Flow</a>

- <a name="git_config">配置 Git 仓库</a>

图1

<img src="https://images-cdn.shimo.im/GuKjruYMv3k84gRu/iosbuild_1.jpg" style="zoom:30%">

环境准备完成后，浏览器进入 flowci web，点击创建 flow  按钮 <图1> 打开 “创建 flow” 界面，填写 flow 名称后进入 “配置 Git 仓库”，如 <图2>。

图2

<img src="https://images-cdn.shimo.im/5WAdLECC6usRM8sd/iosCreateProj.jpg" style="zoom:30%">

这里我们选择 “SSH” 方式连接 Git 仓库并且输入项目 “Git 仓库地址” 。

flowci 触发自动构建需要接收 Git 仓库的 webhook 事件，所以需要 “手动添加 webhook 地址到你的 Git 仓库”，参见：[ 如何添加 webhook 地址到你的 Git 仓库？](./other_faqs.md#add_webhook)

添加完成后回到 flowci “配置 Git 仓库” 界面，点击 “连接测试” 按钮，测试是否成功连接 Git 仓库。测试成功后，点击 “下一步” ，配置 yml 工作流。

- <a name="yml_config">配置 yml 工作流</a>

在输入框中填写 yml 工作流，完成后，flowci 会自动触发第一次 Build。

**之后可以在 “工作流设置” 中修改 yml 工作流配置。**

如何编写 yml 配置文件请参见：[iOS 模板](./yml_ios.md)

### <a name="ios_build_trigger">3、触发构建</a>

图 3

<img src="https://images-cdn.shimo.im/AYFaRGIyccUIbiwv/iosrunbuild.jpg" style="zoom:30%">

创建 flow 成功后，有两种方式触发项目构建：

* 修改项目任一文件并提交，触发构建

* 手动点击 “运行工作流”

点击打开构建详情，可查看构建日志等信息。

图 4

<img src="https://images-cdn.shimo.im/tO03tDIS7MYAY07H/iosbuildlog.jpg" style="zoom:30%">


### <a name="ios_get_ipa">4、获取产物</a>

打开构建日志 “Get_Artifacts_File” 根据产物输出路径获取产物。


<br/><br/><br/>
<div id="bom">
<a href="./other_faqs.md">下一节：常见问题 Faq </a>
</div>
<link rel="stylesheet" rev="stylesheet" href="flow.css" type="text/css"/> 
