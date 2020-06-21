# YAML References

* [`envs`](##envs)
* [`trigger`](##trigger)
* [`selector`](##selector)
* [`cron`](##cron)
* [`steps`](##steps)
  * [`name`](####name)
  * [`allow_failure`](####allow_failure)
  * [`envs`](####envs)
  * [`script`](####script)
  * [`docker`](####docker)
    * `image`
    * `ports`
    * `user`
    * `entrypoint`
    * `stop_on_finish`
    * `delete_on_finish`
  * [`plugin`](####plugin)
  * [`exports`](####exports)

-----------

## `envs`

Environment variables that will effected in all steps

```yaml
envs:
  FIRST_ENV: "first var"
  SECOND_ENV: "hello world"
```

## `trigger`

When push your code, open/close pull request, or create a tag, the source control management system automatically sends a webhook to flow.ci which in turn triggers flow execution. Use the trigger section to limit the execution. The flow will be executed anyway if this section not defined.
  
```yaml
trigger:
  branch:
    - "develop"
    - "master"
    - "feature/*"
  tag:
    - "*"
```

## `selector`

Find out matched agents to run flow job by label, or any idle agents if the tag not defined

```yaml
selector:
  label:
    - ios
    - local
```

## `cron`

config crontab exeuction for flow

```yaml
cron: "* * * * *"
```

## `steps`

#### `name`

Specify a custom step name, rather than a generated default name (ex: step-1)

```yml
steps:
- name: step name
```

#### `allow_failure`

the flow will be failed if something wrong in the script while value is `false`. Ignore the error and mark step status to passed if value is `true`, the default value is `false`.

```yml
steps:
- name: step name
  allow_failure: true
```

#### `envs`

define environment variables scoped to individual steps.

```yml
steps:
- name: step name
  allow_failure: true
  envs:
  - MY_ENV: "hello"
```

#### `script`

the bash script will be executed.

```yml
steps:
- name: step name
  allow_failure: true
  envs:
  - MY_ENV: "hello"
  script: |
    echo $MY_ENV
```

#### `docker`

if `docker` tag applied, the script in `script` will be run within docker

```yml
steps:
- name: step name
  allow_failure: true
  envs:
  - MY_ENV: "hello"
  docker:
    image: ubuntu:18.04
    ports: # optional
    - "8080:8080"
    - "9090:9090"
    user: admin # optiona, default is root
    entrypoint: # optional, default is "/bin/bash"
    - "/bin/bash"
    stop_on_finish: 'true' # optional, default is true
    delete_on_finish: 'ture' # optiaon, default is true
  script: |
    echo $MY_ENV
```

#### `plugin`

Apply plugin in the step

> the `script` tag will be optional, if script specified, it will be executed before plugin

```yml
steps:
- name: run unit test
  envs:
    - ENV_FOR_PLUGIN: "xxx"
  plugin: 'maven-test' # the plugin name
```

#### `exports`

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