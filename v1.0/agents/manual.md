# Manual Setup Agent

Agent is the application to run flow jobs, you have to create an Agent before job started.

## 1. Create from Admin page

* Click `Settings` -> `Agents` -> `+`

    ![where_to_create_agent](./img/where_to_create_agent.png)

* Specify unique agent name
* Specify tag (optional)

    Agent tag is used for flow which has `selector` configuration in YAML, that means the flow job runs only on the agent with matched tags.

    For example, if flow YAML specified `selector` like the following, so that  job will runs only on Agents with tag `ios`.

    ```yaml
    selector:
    tags:
        - ios
    ```

* Click `Save`

    The created agent will be shown on the list

    ![agent status](./img/agent_status.png)

## 2. Start Agent

The most easiest way is start agent from [flow-docker](https://github.com/flowci/docker) repo by run `./agent.sh` script.

Or from the following script, and replace the value of `FLOWCI_SERVER_URL` and `FLOWCI_AGENT_TOKEN`

```bash
docker volume create pyenv
docker run --rm -v pyenv:/ws flowci/pyenv:1.0 bash -c "~/init-pyenv-volume.sh"

docker run -it \
-e FLOWCI_SERVER_URL=http://yourhost:port \
-e FLOWCI_AGENT_TOKEN=token_copied_from_admin_page \
-e FLOWCI_AGENT_VOLUMES="name=pyenv,dest=/ci/python,script=init.sh" \
-v /var/run/docker.sock:/var/run/docker.sock \
flowci/agent
```

#### Start from binary

build agent binary from repo

```bash
git clone https://github.com/FlowCI/flow-agent-x.git
cd flow-agent-x

make build
ls -l ./bin

##### output ####
# flow-agent-x-linux
# flow-agent-x-mac
```

start from binary

```bash
./bin/flow-agent-x-{your os} -u ci_server_url -t agent_token

#### example ####
# ./bin/flow-agent-x-linux -u http://172.10.20.1:8080 -t 44793491-03ac-4a3c-8c59-1f09b7c9d0e3
```




