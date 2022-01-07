# 开始任务

当配置好工作流 (flow) 后，即可开始一个任务 (job).

开始一个任务，至少需要一个可用的 Agent。 关于如何配置 Agent，请参考[Agent 章节](/cn/agents/index)

## 手动触发

从页面 `http://{your host}/#/flows/{your flow name}/jobs`，点击 `开始` 来执行一个任务

## Git 事件触发

支持的仓库有: [GitHub](https://github.com), [GitLab](https://gitlab.com), [Gogs](https://gogs.io/) 和 [Gitee](https://gitee.com/)

支持的事件有: `Push`, `Tag` 和 `Pull Request`

如何配置 Git 仓库，请参见 [Git 仓库](cn/git/index.md)