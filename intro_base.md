# Getting Started

## 1. Install

Install flow.ci just by running the following command

> [Docker](https://docs.docker.com/install/) & [Docker-Compose](https://docs.docker.com/compose/install/) are required

```bash
git clone https://github.com/FlowCI/docker.git flow-docker
cd flow-docker
./server.sh start
```

## 2. Create a flow

- Give a name
  - Click 'create flow' from left panel
  - Input name of flow
  - The flow will be created directly without Git setup
  
- Git Setup (optional)
  
  > Optional step, it can be done from YAML configuration after flow created

  - Config Git URL

    - `webhook`: url used for receive git events (push, tag, pull request), please using the url shown on 'Webhook' field.
    
    - `git url`: fill in repo remote url copied from git, support both `git@:` and `https://`
  
  - Config Git Access

    Generate an new or reuse an existing ssh-rsa key, which allow read-only or read-write (if enabled) access to your repository: [GitHub](./en/git/github.md), [GitLab](./en/git/github.md), [Gogs](./en/git/github.md)

  - Test Git Connection

    Click 'test' button to test git repo access right, or click 'finish' to create flow without test.

    ![](./en/start/img/create_flow_with_git_test.gif)

## 3. Setup YAML

flow.ci will create a sample yaml after the flow created by default, or try with simple [templates](https://github.com/FlowCI/templates).

For more detail, goto [YAML Configuration](./en/yml/reference_v1.md) chapter

## 4. Setup Agent

flow.ci will automatic setup agent if docker has been installed on your host. Of course you can [setup agent by manually](./en/agents/manual.md)

## 5. Start build

- Manually

  Click `Run` button from flow page

- Trigger (if webhook setup correctly)
  - Push
  - Tag
  - Pull Request

## Demo
  ![](./src/demo.gif)
