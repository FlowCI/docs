# Git Configuration

In this section will guide you how to config Git repo in the flow

## Config Git

### There are some variables that will be applied to [git clone](https://github.com/flowci-plugins/gitclone) plugin

- `FLOWCI_GIT_URL` (required): git http/ssh url, ex: git@github.com:FlowCI/spring-petclinic-sample.git
- `FLOWCI_GIT_REPO` (required): git repo name
- `FLOWCI_GIT_BRANCH`: git branch name, default value is `master`
- `FLOWCI_GIT_COMMIT_ID`: clone from commit id if this variable specified
- `FLOWCI_GIT_CREDENTIAL`: secret name created from admin page, it will be required if git url is based on ssh
- `FLOWCI_GITCLONE_TIMEOUT`: timeout for gitclone in seconds, default is `60` seconds

### Thoese variables could be added either from YAML or UI, for example

- YAML Configuration

    ```yaml
    envs:
        FLOWCI_GIT_URL: "https://github.com/FlowCI/spring-petclinic-sample.git"
        FLOWCI_GIT_BRANCH: "master"
        FLOWCI_GIT_REPO: "spring-petclinic"
        # FLOWCI_GIT_CREDENTIAL: "create a secret from Admin Settings -> Secrets -> +"
        # FLOWCI_GITCLONE_TIEMOUT: 60
    ```

- Flow Variable

    ![git vars](./img/git_settings.png)



## How to setup deploy key (permission) and Webhook (event trigger)

flow.ci currenlty supported webhook from:

- [GitHub](./github.md)
- [GitLab](./gitlab.md)
- [Gogs](./gogs.md)
- [Gitee](./gitee.md)

please click around the links for more detail
