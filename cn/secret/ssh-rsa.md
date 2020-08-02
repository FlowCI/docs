# SSH-RSA 秘钥

## 从管理员设置中创建 SSH-RSA 秘钥

1. 点击 `Settings` -> `Secret` -> `+`
2. 输入一个名称
3. 选择 `SSH Key` 类型
4. 编辑 SSH 公私钥

   - 可以点击 `CREATE NEW SSH KEY` 按钮来创建新的 SSH-RSA 公私钥
   - 或者 copy-paste 已有的公私钥
5. 保存 `Save`

![create ssh rsa](../../src/secret/create_ssh_key.gif)

## 如何使用

- 在插件中应用，例如 `gitclone` 插件，需要配置 Git 的访问权限，只需要在 YAML 中输入所创建的秘钥名称即可

  ```yml
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

- [SSH 主机中配置访问权限](../agents/ssh_host.md)
