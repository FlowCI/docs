# flow.ci

Open-source CI/CD server that makes DevOps easier.

- Getting started within a minute

- Simple YAML configuration and templates

- Elastic Agents to speed up build

- Online TTY to debug your job in time

- Flexible plugins

- Run steps on any docker images or native os

## Quick Start

> [Docker](https://docs.docker.com/install/) & [Docker-Compose](https://docs.docker.com/compose/install/) are required

```bash
git clone https://github.com/FlowCI/docker.git flow-docker
cd flow-docker
./server.sh start
```

## [Document]() | [中文文档]()


![](./v1.0/img/demo.gif)


## Table of contents

* Getting Started
  * [First Build](./v1.0/start/index.md)

* YAML
  * [Reference](./v1.0/yml/reference_v1.md)
  * [Plugins](./v1.0/yml/plugins.md)
  * [Templates](https://github.com/FlowCI/templates)

* Link to Git
  * [Github](./v1.0/git/github.md)
  * [Gitlab](./v1.0/git/gitlab.md)
  * [Gogs](./v1.0/git/gogs.md)

* Agents
  * [Manual Setup](./v1.0/agents/manual.md)
  * Auto Scaling
    * [Scaling On Host](./v1.0/agents/ssh_host.md)
    * [Scaling On K8s](./v1.0/agents/k8s_host.md)

* Credential
  * [SSH-RSA](./v1.0/credential/ssh-rsa.md)
  * [Auth (username and password)](./v1.0/credential/auth.md)
