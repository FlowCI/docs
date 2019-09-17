# YAML Reference

Example

    ```yaml
    envs:
      MY_VERSION: "echo version"

    cron: "* * * * *"

    filter:
      branches:
      - "develop"
      - "master"
      - "feature/*"
      tags:
      - "*"

    selector:
      tags:
      - ios
      - local

    steps:
    - name: say-hello
      allow_failure: true
      envs:
        HELLO: "say hello"
      script: |
        echo "${HELLO} to ${MY_VERSION}"
        export TO_NEXT_STEP="hello again"
      exports:
        - "TO_NEXT_STEP"

    - name: say-hello-again
      script: |
        echo "${TO_NEXT_STEP}"

    ```

- `env` (optional): environment variables in flow level shared in all steps.

  ```yaml
  envs:
    FIRST_ENV: "first var"
    SECOND_ENV: "hello world"
  ```

- `trigger` (optional)
  - `branches` (optional): config which branches will trigger the flow
  - `tags` (optional): config which tags will trigger the flow
  
  ```yaml
  filter:
    branches:
    - "develop"
    - "master"
    - "feature/*"
    tags:
    - "*"
  ```

- `selector` (optional)
  - `tags`: to select which agent can be work for the flow by agent tags

  ```yaml
    selector:
      tags:
      - ios
      - local
    ```

- `cron`: (optional): config crontab job for flow

  ```yaml
  cron: "* * * * *"
  ```

- `steps`: steps are defined as a series of shell commands

  - `name` (optional): define the name of step, it will create a default name (ex: step-x) if this field not defined.

  - `allow_failure` (optional): the flow will be failed if something wrong in the script while value is `false`. Ignore the error and mark step status to passed if value is `true`, the default value is `false`.
  
  - `envs`: (optional): define environment variables scoped to individual steps.

  - `script`: the shell script will be executed under the flow level directory.

  - `exports` (optional): define environment variables that will passed to the following steps.
