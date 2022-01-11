# SSH-RSA Secret

## Create

1. Click `Settings` -> `Secret` -> `+`
2. Enter a secret name
3. Select `SSH_RSA` in category field
4. Edit key pair

    - create new key pair by click `CREATE NEW SSH KEY` button, it will generate new ssh-rsa key pair from current user email
    - or copy-paste key pair to text box
5. save

![create ssh rsa](../../_images/secret/create_ssh_key.gif)

## How to

- `git-clone` plugin: just need to type the secret name as value for variable `FLOWCI_GIT_CREDENTIAL`

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

- Auto scaling Agent: please refer [SSH Host](en/agents/ssh_host.md#auto-scalling-on-a-host-via-SSH)

- Access `SSH-RSA` secret from script

  It can be accessed from script if the `secrets` has beed defined from step YAML
  
  ```yaml
  steps:
    - name: get sshrsa demo
      secrets:
      - my_ssh_key
      bash: |
        echo ${my_ssh_key_PUBLIC_KEY}
        echo ${my_ssh_key_PRIVATE_KEY}
  ```