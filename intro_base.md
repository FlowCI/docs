# Getting Started [快速开始](./zh/start/index.md)

## 1. Install

> [Docker](https://docs.docker.com/install/) & [Docker-Compose](https://docs.docker.com/compose/install/) are required

To install flow.ci, just run the following script:

```bash
git clone https://github.com/FlowCI/docker.git flow-docker
cd flow-docker
./server.sh start
```

Open the link `http://localhost:2015` from web browser after installtion is finished, and login in with default username `admin@flow.ci` and password `example`.

![cmd](./src/start_server.gif)

## 2. Create a flow

- Input flow name
  - Click 'create flow' button
  - Input name of flow
  
- Select YAML template

## 3. First build

Click `Run` button from flow page

> - Job cannot started if the blank template has been selected.
> - How to config Git repo, please refer to [Link to Git](./en/git/index.md)

![start](./src/create_flow_and_build.gif)
