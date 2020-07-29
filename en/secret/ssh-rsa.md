# SSH-RSA Secret

## Create a SSH-RSA Secret from admin page

1. Click `Settings` -> `Secret` -> `+`
2. Enter a secret name
3. Select `SSH_RSA` in category field
4. Edit key pair

    - create new key pair by click `CREATE NEW SSH KEY` button, it will generate new ssh-rsa key pair from current user email
    - or copy-paste key pair to text box
5. save

![create ssh rsa](../../src/secret/create_ssh_key.gif)

## How to use it

- Plugin

  Some of the plugins need secret to gain access. For example `git-clone` plugin, it requires a ssh-rsa secret to clone the git repo, it's pretty easy to use the secret by type the secret name your created.

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

- [SSH Host](../agents/ssh_host.md)