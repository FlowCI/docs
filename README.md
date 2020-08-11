<h3 align="center">
  <a href="https://flowci.github.io">
    <img src="https://github.com/FlowCI/docs/raw/master/src/flow.ci.png" alt="fastlane Logo" width="150">
  </a>
</h3>

<h4 align="center">flow.ci is a powerful and user-friendly CI/CD server</h4>

[![LICENSE](https://img.shields.io/github/license/pingcap/tidb.svg)](https://github.com/pingcap/tidb/blob/master/LICENSE)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/flowci/flow-core-x)

## Key Features

- Zero configuration, can be getting started within a minute

- Simple YAML configuration and templates

- Elastic agents to speed up build

- Online TTY to debug your job in time

- Flexible plugins

- Run steps either on any docker images or native os

## Document

[English](https://github.com/FlowCI/docs/tree/master/en/index.md) | [中文文档](https://github.com/FlowCI/docs/tree/master/cn/index.md)

## Templates

[maven, npm, golang, ruby, android and more](https://github.com/FlowCI/templates)

## Installation

> [Docker](https://docs.docker.com/install/) & [Docker-Compose](https://docs.docker.com/compose/install/) are required

```bash
git clone https://github.com/FlowCI/docker.git flow-docker
cd flow-docker
./server.sh start
```

## Preview

![demo](https://github.com/FlowCI/docs/raw/master/src/demo.gif)

![tty](https://github.com/FlowCI/docs/raw/master/src/step_tty.gif)
