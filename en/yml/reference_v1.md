# YAML References

* [`envs`](#envs)
* [`condition`](#condition)
* [`selector`](#selector)
* [`docker` / `dockers`](#docker/dockers)
  * `image`
  * `name`
  * `ports`
  * `user`
  * `entrypoint`
  * `command`
  * `environment`
  * `network`
  * `is_runtime`
  * `stop_on_finish`
  * `delete_on_finish`
* [`notifications`](#notifications)
  * `plugin`
  * `envs`
* [`steps`](#steps)
  * [`name`](#name)
  * [`condition`](#condition)
  * [`allow_failure`](#allow_failure)
  * [`retry`](#retry)
  * [`timeout`](#timeout)
  * [`envs`](#envs)
  * [`bash`](#bash)
  * [`pwsh`](#pwsh)
  * [`docker` / `dockers`](#docker/dockers)
    * `image`
    * `name`
    * `ports`
    * `user`
    * `entrypoint`
    * `command`
    * `environment`
    * `network`
    * `is_runtime`
    * `stop_on_finish`
    * `delete_on_finish`
  * [`plugin`](#plugin)
  * [`exports`](#exports)

-----------

## envs

Environment variables that will effected in all steps

```yaml
envs:
  FIRST_ENV: "first var"
  SECOND_ENV: "hello world"
```

## condition

The Groovy script return boolean value to define the flow starting condition, the list of environment variables in [here (Git section only)](../agents/vars.md).

> The conditon will be ignored while start a job from manual
  
for example: the following defined the flow can be started when branch is `master` from github.

```yaml
condition: |
  return FLOWCI_GIT_BRANCH == "master" && FLOWCI_GIT_SOURCE == "GITHUB"
```

## selector

Find out matched agents to run flow job by label, or any idle agents if the tag not defined

```yaml
selector:
  label:
    - ios
    - local
```

## docker/dockers

if `docker` / `dockers` tag applied, all steps will be run within docker container

> the default network is `flow-ci-agent-default`

### single docker

```yml
docker:
  image: ubuntu:18.04
  name: your_container_name # optional
  ports: # optional
  - "8080:8080"
  - "9090:9090"
  user: root # optiona, default is root
  entrypoint: # optional, default is "/bin/bash"
  - "/bin/bash"
  stop_on_finish: 'true' # optional, default is true
  delete_on_finish: 'ture' # optiaon, default is true

steps:
- name: step name
  allow_failure: true
  envs:
    MY_ENV: "hello"
  script: |
    echo $MY_ENV
```

### multiple docker

```yml
dockers:
- image: ubuntu:18.04
  entrypoint: ["/bin/bash"] # optional, default is /bin/bash for runtime image
  is_runtime: true # default runtime for steps

- image: mysql:5.6
  environment: # optional: environment for docker only
    MYSQL_ROOT_PASSWORD: my_password
  ports: # optional
  - "3306:3306"
  user: root # optiona, default is root
  entrypoint: [] # optional, default is empty
  command: [] # optional, default is empty
  network: "flow-ci-agent-default" # optional, default is flow-ci-agent-default
  stop_on_finish: 'true' # optional, default is true
  delete_on_finish: 'ture' # optiaon, default is true

- image: rabbitmq:3

steps:
- name: step name
  allow_failure: true
  envs:
    MY_ENV: "hello"
  script: |
    echo $MY_ENV
```

## notifications

It will run plugin with tag `notification` in server side, to send notification when job finished

```yaml
notifications:
- plugin: 'email-notify'
  envs:
    FLOWCI_SMTP_CONFIG: 'test-config'
```

## steps

#### name

Specify a custom step name, rather than a generated default name (ex: step-1)

```yml
steps:
- name: step name
```

#### condition

The Groovy script return boolean value to define the step can be run or not

```yml
steps:
- name: step name
  envs:
    my_var: "hello"
  conditon: |
    ## groovy script that return boolean value
    return "$my_var" == "hello";
```

#### allow_failure

the flow will be failed if something wrong in the script while value is `false`. Ignore the error and mark step status to passed if value is `true`, the default value is `false`.

```yml
steps:
- name: step name
  allow_failure: true
```

#### retry

define number of times to retry the step when it's fail

```yml
steps:
- name: step name
  allow_failure: true
  retry: 5
  bash:
    echo "start"
    fail_here.
```

#### timeout

define step timeout in seconds

```yml
steps:
- name: step name
  allow_failure: true
  timeout: 3600
  bash:
    echo "start"
    sleep 1000
```

#### envs

define environment variables scoped to individual steps.

```yml
steps:
- name: step name
  allow_failure: true
  envs:
    MY_ENV: "hello"
```

#### bash

the Bash script will be executed.

```yml
steps:
- name: step name
  allow_failure: true
  envs:
    MY_ENV: "hello"
  bash: |
    echo $MY_ENV
```

#### pwsh

the PowerShell script will be executed under Windows Agent

```yml
steps:
- name: step name
  allow_failure: true
  envs:
    MY_ENV: "hello"
  pwsh: |
    echo $Env:MY_ENV
```

#### docker/docker

higher priority than flow level docker section, for detail please refer to flow level [`docker` / `dockers`](#docker/dockers)

#### plugin

Apply plugin in the step

> the `script` tag will be optional, if script specified, it will be executed before plugin

```yml
steps:
- name: run unit test
  envs:
    ENV_FOR_PLUGIN: "xxx"
  plugin: 'maven-test' # the plugin name
```

#### exports

define environment variables that will passed to job context, and available for flowing steps

```yml
steps:
- name: step name
  script: |
    echo $MY_ENV
    export ENV_FOR_NEXT_STEP="hello"
  exports:
  - "ENV_FOR_NEXT_STEP"
```
