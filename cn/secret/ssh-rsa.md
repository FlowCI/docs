# `SSH-RSA` 类型的秘钥

## 创建密钥

1. 点击 `Settings` -> `Secret` -> `+`
2. 输入一个名称
3. 选择 `SSH Key` 类型
4. 编辑 SSH 公私钥
   - 可以点击 `CREATE NEW SSH KEY` 按钮来创建新的 SSH-RSA 公私钥
   - 或者拷贝已有的公私钥
5. 保存 `Save`

![create ssh rsa](../../images/secret/create_ssh_key.gif)

## 如何使用

- `gitclone` 插件中使用: 只需要在 `FLOWCI_GIT_CREDENTIAL` 变量中输入所创建的秘钥名称即可

  ```yaml
  envs:
    FLOWCI_GIT_URL: "https://github.com/FlowCI/spring-petclinic-sample.git"
    FLOWCI_GIT_BRANCH: "master"
    FLOWCI_GIT_REPO: "spring-petclinic"

  steps:
  - name: clone
    envs:
      FLOWCI_GIT_CREDENTIAL: "rsa-test"
    plugin: 'gitclone'
  ```

- 配置 SSH 类型的可伸缩 Agent 中使用，[请参考](cn/agents/ssh_host.md#可伸缩-agent-配置-ssh-主机)

- 从 `Step` 中获取 `SSH-RSA` 密钥

  例如: 创建了一个名为 `my_ssh_key` 的 `SSH-RSA` 类型的密钥，可以在 YAML 配置中，通过 `secrets` 引入

  ```yaml
  steps:
    - name: get sshrsa demo
      secrets:
      - my_ssh_key
      bash: |
        echo ${my_ssh_key_PUBLIC_KEY}
        echo ${my_ssh_key_PRIVATE_KEY}
  ```
