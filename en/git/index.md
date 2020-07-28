# Git Configuration

## Clone Git Repo

flow.ci clone git repo by plugin [git clone](https://github.com/flowci-plugins/gitclone)

```yaml
steps:
- name: clone
  docker:
    image: flowci/debian-git ## other images with git command can be applied here as well
  plugin: 'gitclone'
```

You can config git repo url via YAML and UI. The variable `FLOWCI_GIT_CREDENTIAL` must be defined if git url is based on SSH.

- YAML configuration

  ```yaml
  envs:
    FLOWCI_GIT_URL: "https://github.com/FlowCI/spring-petclinic-sample.git"
    # FLOWCI_GIT_CREDENTIAL: your_secret_name, created from secret from Admin Settings -> Secrets -> +
  ```

- Web UI configuration

  ![git vars](../../src/git/git_settings.png)

## Config permission and event triger

flow.ci currenlty supported git repo are:

- [GitHub](./github.md)
- [GitLab](./gitlab.md)
- [Gogs](./gogs.md)
- [Gitee](./gitee.md)

please click around the links for more detail
