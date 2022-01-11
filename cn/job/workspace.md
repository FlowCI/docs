# 工作区 (workspace)

__工作区__ 是一个在 Agent 中的文件路径，每个工作流下的任务，都 __共享__ 同一个工作区。

该工作区为脚本的默认路径，也可以通过变量 `FLOWCI_AGENT_JOB_DIR` 访问。

- Agent 从 `Docker` 启动: `/ws/{flow id}`
- Agent 从 `可执行程序` 启动: 默认路径为 `${HOME}/.flow.ci.agent/{flow id}`

如果需要存储 任务(job) 特有的数据，可以创建该任务所对应的目录:

```yaml
steps:
- name: job_own_dir
  bash: |
    # 根据 任务编号 创建文件夹
    mkdir -p "${FLOWCI_AGENT_JOB_DIR}/${FLOWCI_JOB_BUILD_NUM}"

- name: access_job_dir
  bash: |
    # 访问该文件夹
    cd "${FLOWCI_AGENT_JOB_DIR}/${FLOWCI_JOB_BUILD_NUM}"
```