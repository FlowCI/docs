# Run Condition

Every jobs or steps could apply a starting condition with `Groovy` script.

The [variables](en/agents/vars.md) could be used in the `Groovy` script, the return value of `Groovy` should be `boolean`, for example:

```yaml
 - condition: |
     println("hello world")
     true
```

## Condition for Job

Set `condition` in the YAML root

__Example__: Job only can be started at branch `master` or `develop`

```yaml
condition: |
  return $FLOWCI_GIT_BRANCH == "develop" || $FLOWCI_GIT_BRANCH == "master";

steps:
- name: step1
  bash: |
    echo "this is the step one"
```

## Condition for Step

Set `condition` in the step YAML, the step will be __skipped__ when the condtion script return `false`

__Example__: `step2` will be executed directly since `step1` return `false`

```yaml
steps:
- name: step1
  condition: |
    return false
  bash: |
    echo "this is the step one"

- name: step2
  condition: |
    return true
  bash: |
    echo "this is the step two"
```