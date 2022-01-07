# 运行条件

每一个任务(job) 或 执行步骤(step) 都可以使用 `Groovy` 脚步自定义执行条件。


在 `Groovy` 脚本中，可以使用 [flow.ci 的环境变量](cn/agents/vars.md), 要求返回值为 `boolean`, 例如:

```yaml
 - condition: |
     println("hello world")
     true
```


## 任务的运行条件

在工作流 YAML 配置中，根节点添加 `condition`。

__例如__: 指定任务只能在 "develop" 或 "master" 分支改变时运行

```yaml
condition: |
  return $FLOWCI_GIT_BRANCH == "develop" || $FLOWCI_GIT_BRANCH == "master";

steps:
- name: step1
  bash: |
    echo "this is the step one"

```


## 步骤 (step) 的运行条件

每个步骤 (step) 都可以定义对应的运行条件，如果条件不满足时，会 __跳过__ 该步骤。

__例如__: `step1` 中返回值为 `false`, 运行时则会跳过该步骤，直接执行 `step2`

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