# 连接 GitLab

## 添加访问权限

- 从 `Settings -> Secret` 中 copy 相应的公钥
- 打开 GitLab 页面，在项目设置 `Settings > Repository -> Deploy Keys`
- Paste 公钥，保存后，flow.ci 就可获得该 GitLab 项目的访问权限

> GitLab 不可以在多个项目中使用同一个公钥， 如果需要用同一个公钥访问多个仓库，建议在 GitLab 中创建一个特殊的用户比如 `CI User`，之后再该用户中添加 SSH 公钥。

![gitlab_setup_deploy_key](../../_images/git/gitlab_setup_deploy_key.png)

## 配置 Git 触发事件 (Webhook)

触发事件（Webhook）是用于当有 Push，Tag 或者 Pull Request 等操作时时，触发 CI 任务。

1. 从工作流设置中复制 webhook 链接
   > 提示: 当前 CI 的主机需要有公网能访问的 IP 或者 域名，否则无法收到触发事件。如果无法配置公网访问，可以使用 [ngrok](https://ngrok.com/) 等工具来获取公网 -> 内网映射。

   ![webhook settings](../../_images/git/select_webhook_url.gif)

2. 设置 GitLab webhook

- URL: 粘贴 webhook 链接

  > 如果使用 `ngrok`, 请手动替换地址的第一部分, 例如: `http://172.20.10.4/webhooks/spring-sample` to `http://7e9ea9dc.ngrok.io/webhooks/spring-sample`

- 选择触发事件
  
  选择事件 `Push events`, `Tag push events` 和 `Merge request events`
  
  ![events](../../_images/git/gitlab_setup_webhook.png)

## 验证 GitLab 配置

- 验证权限:
  
  可以点击 `Test` 按钮验证访问权限是否配置正确.

  ![gitlab_test](../../_images/git/gitlab_test_config.gif)