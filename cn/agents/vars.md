# 任务运行时可使用的环境变量

## 通用的

- `FLOWCI_SERVER_URL`

- `FLOWCI_FLOW_NAME`

- `FLOWCI_FLOW_WEBHOOK`

## 任务 (Job) 相关

- `FLOWCI_JOB_BUILD_NUM`

- `FLOWCI_JOB_STATUS`

- `FLOWCI_JOB_TRIGGER`

- `FLOWCI_JOB_URL`

- `FLOWCI_JOB_START_AT`

- `FLOWCI_JOB_FINISH_AT`

- `FLOWCI_JOB_DURATION`

## Agent 相关

- `FLOWCI_AGENT_TOKEN`

- `FLOWCI_AGENT_PORT`

- `FLOWCI_AGENT_WORKSPACE`

- `FLOWCI_AGENT_JOB_DIR`

- `FLOWCI_AGENT_PLUGIN_DIR`

- `FLOWCI_AGENT_IP_{interface name}`: interface name for example: en0, en1

## Docker 容器相关 (当 step 中定义了 docker 内容时有效)

- `FLOWCI_AGENT_DOCKER_NETWORK`: 当前 Docker network 名称

- `CONTAINER_ID_{container index}`: container index start from 0

- `CONTAINER_IP_{container index}`

## Git 相关

- `FLOWCI_GIT_REPO`

- `FLOWCI_GIT_SOURCE`: `GITHUB` | `GITLAB` | `GOGS` |  `GITEE`

- `FLOWCI_GIT_EVENT`: `PUSH` | `TAG` | `PR_OPENED` | `PR_MERGED`

#### Push / Tag 事件

- `FLOWCI_GIT_BRANCH`

- `FLOWCI_GIT_AUTHOR`

- `FLOWCI_GIT_COMMIT_MESSAGE`: 最后一个 Commit 的描述

- `FLOWCI_GIT_COMMIT_TOTAL`: 

- `FLOWCI_GIT_COMMIT_LIST`: commit 列表, base64格式. 例如: `base64([{id:xx, message: xxx, time:xxx, url: xxx, author: {name: xx, email: xx}}, {xxx}, ...])`

#### Pull Request 事件

- `FLOWCI_GIT_PR_TITLE`

- `FLOWCI_GIT_PR_MESSAGE`

- `FLOWCI_GIT_PR_URL`

- `FLOWCI_GIT_PR_TIME`

- `FLOWCI_GIT_PR_NUMBER`

- `FLOWCI_GIT_PR_HEAD_REPO_NAME`

- `FLOWCI_GIT_PR_HEAD_REPO_BRANCH`

- `FLOWCI_GIT_PR_HEAD_REPO_COMMIT`

- `FLOWCI_GIT_PR_BASE_REPO_NAME`

- `FLOWCI_GIT_PR_BASE_REPO_BRANCH`

- `FLOWCI_GIT_PR_BASE_REPO_COMMIT`
