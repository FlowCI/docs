# Setup GitHub

## - Webhook

The webhook used for receive git notification such as push, tag, pull request and so on.

1. Copy webhook url from flow settings
    > Hint: Your host must be exposed to internet (public ip or domain), otherwide the github events can not be received.
    > If pulbic ip or domain not availble in your environments, please use the tools like [ngrok](https://ngrok.com/).  

   ![webhook settings](./img/github_select_webhook_url.png)

2. Open webhook from GitHub settings

   ![webhook settings](./img/github_webhook_setting.png)

3. Setup webhook

    - Payload URL

      Paste webhook url copied from flow settings (step 1)

      > If using `ngrok`, please replace wehbook url by ngrok, ex: `http://172.20.10.4/webhooks/spring-sample` to `http://7e9ea9dc.ngrok.io/webhooks/spring-sample`

    - Content type

      Select content type to `application/json`

    ![payload and content](./img/github_setup_payload_and_content.png)

4. Select events

    - Select `Let me select individual events`
    - Check events `push` and `pull request`

    ![events](./img/github_select_events.png)

## - Deploy Key

1. Create SSH-RSA
  
   You can create a new or add an existing ssh-rsa to gain git repo access right. 

  - Given a name: name used for identify which ssh-rsa will be applied in the flow
    

  - Create or paste existing 

2. Set variable from YAML

   `FLOWCI_CREDENTIAL_SSH_RSA` to control which ssh-rsa applied in the flow, for example named key as `flow-test-key`, then add this var into your YAML file as following:

   ```yaml
    
    envs:
      FLOWCI_CREDENTIAL_SSH_RSA: "flow-test-key"

    steps:
      script: |
        echo hello
    
   ```

3. Copy to GitHub
  - Single repo
  - All repos


## - Verify Settings

- Webhook:

  The green check box will be shown after 'webhook' field if the flow receive the 'ping' request after GitHub webhook created.

- Deploy Key:
  
  Test the access right from flow settings by click 'test' button, the green will be shown if everything correct.

![github_test](./img/github_test_config.gif)