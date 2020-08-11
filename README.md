
# [flow.ci](https://flowci.github.io)

[![LICENSE](https://img.shields.io/github/license/pingcap/tidb.svg)](https://github.com/pingcap/tidb/blob/master/LICENSE)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/flowci/flow-core-x)

Powerful and user-friendly CI/CD server

## Key Features

- Zero configuration, can be getting started within a minute

- Simple YAML configuration and templates

- Elastic Agents to speed up build

- Online TTY to debug your job in time

- Flexible plugins

- Run steps either on any docker images or native os

## [Document](./en/index.md) | [中文文档](./cn/index.md)

## [Templates (maven, npm, golang, ruby, android..)](./en/index.md)

## Quick Start

> [Docker](https://docs.docker.com/install/) & [Docker-Compose](https://docs.docker.com/compose/install/) are required

```bash
git clone https://github.com/FlowCI/docker.git flow-docker
cd flow-docker
./server.sh start
```

![](./src/demo.gif)
