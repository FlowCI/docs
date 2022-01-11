# Workspace

__Workspace__ is a directory on Agent, every jobs of flow shares the same workspace.

The default directory of step script is workspace, you could use variable `FLOWCI_AGENT_JOB_DIR` 

- Agent from `docker`: `/ws/{flow id}`
- Agent from `binary`: default path is `${HOME}/.flow.ci.agent/{flow id}`

The job specific directory could be created by `FLOWCI_JOB_BUILD_NUM` in the step

```yaml
steps:
- name: job_own_dir
  bash: |
    # Create job directory according to build number
    mkdir -p "${FLOWCI_AGENT_JOB_DIR}/${FLOWCI_JOB_BUILD_NUM}"

- name: access_job_dir
  bash: |
    cd "${FLOWCI_AGENT_JOB_DIR}/${FLOWCI_JOB_BUILD_NUM}"
```