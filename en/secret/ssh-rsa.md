# SSH-RSA Secret

## Create a SSH-RSA Secret

Click `Settings` -> `Secret` -> `+`

1. Enter a secret name
2. Select `SSH_RSA` in category field
3. new ssh-rsa key pair

    by click `CREATE NEW SSH KEY` button, it will generate new ssh-rsa key pair from current user email

    or copy-paste key pair to text box
4. save

![create ssh rsa](./img/ssh_rsa_create.png)

## How to use it

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
