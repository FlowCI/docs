# "Token" 类型的秘钥

## 创建密钥

1. 点击 `Settings` -> `Secret` -> `+`
2. 输入一个名称
3. 选择 `Token` 类型
4. 输入 token 数据
5. 保存

![create token](../../_images/secret/create_token.gif)

## 如何使用

- 从 `Step` 中获取 `Token` 密钥

  例如: 创建了一个名为 `my_token` 的 `Token` 类型的密钥，可以在 YAML 配置中，通过 `secrets` 引入

  ```yaml
  steps:
  - name: get token demo
    secrets:
    - my_token
    bash: |
      echo ${my_token}
  ```