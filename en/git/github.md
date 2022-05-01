# GitHub Configuration

## Setup Access Permission for Private Repo

Copy `public key` from admin page, open GitHub repo web and add it from `Settings > Deploy key` for single repo access. GitHub not allowed to add same public key for muliple repositories, we recommend to have a special 'CI user' to manage single public key access: [adding new ssh key to your GitHub account](https://help.github.com/en/articles/adding-a-new-ssh-key-to-your-github-account).

![github_setup_deploy_key](../../_images/git/github_setup_deploy_key.png)

## Setup Webhook

The webhook used for receive git notification such as push, tag, pull request and so on.

1. Copy webhook url from flow settings
    > Hint: Your host must be exposed to internet (public ip or domain), otherwide the GitHub events can not be received.
    > If pulbic ip or domain not availble in your environments, please use the tools like [ngrok](https://ngrok.com/).  

   ![webhook settings](../../_images/git/select_webhook_url.gif)

2. Setup webhook

- Payload URL

  Paste webhook url copied from flow settings (step 1)

  > If using `ngrok`, please replace wehbook url by ngrok, ex: `http://172.20.10.4/webhooks/spring-sample` to `http://7e9ea9dc.ngrok.io/webhooks/spring-sample`

- Content type

  Select content type to `application/json`

  ![payload and content](../../_images/git/github_setup_payload_and_content.png)

- Select events

  - Select `Let me select individual events`
  - Check events `push` and `pull request`

  ![events](../../_images/git/github_select_events.png)

## Verify GitHub Settings

- Webhook:

  The green check box will be shown after 'webhook' field if the flow receive the 'ping' request after GitHub webhook created.

- Permission for repo:
  
  Test the access right from flow settings by click 'test' button, the green will be shown if everything correct.

  ![github_test](../../_images/git/github_test_config.gif)


## Setup Access permission to Write Job Status to GitHub

1. Create a Token

    In order to have permission for writing job status back to GitHub, we need to create a token with `repo:status` scope from https://github.com/settings/tokens

    ![create token](../../_images/git/github_create_access_token.png)

2. Add GitHub Token to flow.ci Secret

    Open the secret settings page `Settings -> Secret -> +` , paste the token copied from Github and save

    ![add token](../../_images/git/add_token.png)

3. Link to GitHub

    Open the git connection page `Settings -> Git -> +`, select `GitHub` on git source, and select a secret created on the last step

    ![link](../../_images/git/github_add_link.png)

4. GitHub commit status

    After the configuration, the correspond commit status will be updated after job finished.

    ![demo](../../_images/git/github_check_updated.png)