# Getting Started

## Create flow (pipeline)

Here the flow almost means pipeline in CI area, but we think flow.ci should be more than CI.

Steps to create flow

- Give a name
  - Click 'create flow' from left panel
  - Type a name for flow
  - The flow will be created directly without Git setup

  ![create_flow](https://github.com/FlowCI/files/blob/master/imgs/create_flow_with_name_only.gif?raw=true)
  
- Git Setup (optional)
  
  > Optional step, it can be done from YML configuraiton

  - Git URL

    Fill in repo remote url copied from git, support both `git@:` and `https://`
  
  - Setup webhook

    The webhook used for receive git events (push, tag, pull request), please using the url shown on 'Webhook' field.

    - How to on [GitHub](../git/github.md)

  - SSH-RSA key
  - Test connection

## Setup YAML

By default, flow.ci will create a sample yaml after the flow created, of course you could change it from UI.

For more detail of YAML configuration please go to [YAML Configuration]() chapter

## Start build
