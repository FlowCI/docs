# 从 Docker 安装 flow.ci

## 安装 Docker 环境

> 如何安装 Docker 以及具体的安装步骤请查看 [Docker 官方文档](https://docs.docker.com/)

## 从 Docker Hub 镜像启动

flow.ci 在 Docker Hub 上提供了最新的镜像，用户可以方便的获取最新的镜像并开始 flow.ci 之旅。

1. 克隆 Docker 构建仓库

	> 在 flow.ci 的 Docker 构建仓库中，提供了快速启动以及相关的服务器配置
	
	- 通过 Git 的形式 Clone 代码，确保机器已经安装了 Git
	
	  `git clone git@github.com:FlowCI/docker.git`
	  
	- 直接通过 http 下载的形式下载代码，之后解压缩
	   
		`curl -L -o docker.zip https://github.com/FlowCI/docker/archive/master.zip`

2. 从 Docker 启动 flow.ci

    进入到上一步获取的代码目录，并执行 `./start-services.sh`， 之后可以访问 `http://localhost:3000` 进入 flow.ci。
    
	例如：在步骤1中代码目录为 `docker`，则可以通过以下命令启动
	
	```bash
	cd docker
	./start-services.sh
	```

	> 环境变量的设置:
	> 
	> - FLOW_API_DOMAIN： 部署的后端 API 域名地址， 默认：http://localhost:8080 
	> - FLOW_WEB_DOMAIN： 部署的前端 Web 页面的域名地址，默认：http://localhost:3000 
	> - FLOW_WS_URL：部署的 API 的 web socket 地址，默认：ws://localhost:8080, 此地址需要和 `FLOW_API_DOMIN` 域名相同 
	> - FLOW_SYS_EMAIL：flow.ci 系统管理员账号，默认是 `admin@flow.ci `
	> - FLOW_SYS_USERNAME：flow.ci 系统管理员的用户名，默认是 `admin` 
	> - FLOW_SYS_PASSWORD: flow.ci 系统管理员密码，默认是 `123456`


## 自己构建 Docker 镜像