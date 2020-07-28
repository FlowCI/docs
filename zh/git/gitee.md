# Gitee Configuration

## Setup Deploy Key

1. Create SSH-RSA
  
   Create a new ssh-rsa or add an existing to gain git repo access right.

    - Specify a name: to identify which ssh-rsa will be applied, for example: `rsa-test`
    - Generate new or peast existing public and private key

    ![how to create ssh-rsa secret](../secret/img/ssh_rsa_create.png)

2. Gitee setup

    Copy `public key` from admin page, open Gitee repo web and add it from `Settings > Deploy keys -> Add key` for single repo access. Gitee not allowed to add same public key for muliple repositories, we recommend to have a special 'CI user' to manage single public key access.

    ![github_setup_deploy_key](./img/gitee_setup_deploy_key.png)

3. Add to YAML

   `FLOWCI_GIT_CREDENTIAL` is used for [git clone plugin](https://github.com/flowci-plugins/gitclone). Example:

   ```yaml
    envs:
      FLOWCI_GIT_CREDENTIAL: "rsa-test"

    steps:
    - name: clone
      plugin: 'gitclone'
   ```
  
    or

   ```yaml
    steps:
    - name: clone
      envs:
        FLOWCI_GIT_CREDENTIAL: "rsa-test"
      plugin: 'gitclone'
   ```

## Setup Webhook

The webhook used for receive git notification such as push, tag, pull request and so on.

1. Copy webhook url from flow settings
    > Hint: Your host must be exposed to internet (public ip or domain), otherwide the GitHub events can not be received.
    > If pulbic ip or domain not availble in your environments, please use the tools like [ngrok](https://ngrok.com/).  

   ![webhook settings](./img/github_select_webhook_url.png)

2. Setup webhook

  - Payload URL

    Paste webhook url copied from flow settings (step 1)

    > If using `ngrok`, please replace wehbook url by ngrok, ex: `http://172.20.10.4/webhooks/spring-sample` to `http://7e9ea9dc.ngrok.io/webhooks/spring-sample`

  - Select events

    Check events `Push`, `Tag Push` and `Pull Request`

    ![events](./img/gitee_setup_webhook.png)

## Verify Gitee Settings

- Webhook:

  The green check box will be shown on 'webhook' field if the flow receive the 'ping' request by click 'Test' button on Gitee webhook page.

- Deploy Key:
  
  Test the access right from flow settings by click 'test' button, the green will be shown if everything correct.

  ![gitlab_test](./img/gitee_test_config.gif)