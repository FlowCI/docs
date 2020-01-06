# YAML References

## `env`

```yaml
envs:
  FIRST_ENV: "first var"
  SECOND_ENV: "hello world"
```

## `trigger`
  

```yaml
trigger:
  branches:
    - "develop"
    - "master"
    - "feature/*"
  tags:
    - "*"
```

## `selector`

Find out matched agents to run flow job by tags, or any idle agent if the tag not defined

```yaml
selector:
  tags:
    - ios
    - local
```

## `cron`

config crontab job for flow

```yaml
cron: "* * * * *"
```

## `steps`

### `name`

Specify a custom step name, rather than a generated default name (ex: step-1)

```yml
steps:
- name: step name
```

### `allow_failure`

the flow will be failed if something wrong in the script while value is `false`. Ignore the error and mark step status to passed if value is `true`, the default value is `false`.

```yml
steps:
- name: step name
  allow_failure: true
```

### `envs`

define environment variables scoped to individual steps.

```yml
steps:
- name: step name
  allow_failure: true
  envs:
  - MY_ENV: "hello"
```

### `script`

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

### `plugin`

Apply plugin in the step

> the `script` tag not working if `plugin` was defined

```yml
steps:
- name: run unit test
  envs:
    - ENV_FOR_PLUGIN: "xxx"
  plugin: 'maven-test' # the plugin name
```

### `exports`

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
