# Start a job

A job could be started after the YAML configuraiton of flow is ready.

At least one Agent is required for starting a job, please refer [Agent](/en/agents/index) for how to setup agent

## Run manually

Click 'RUN' button from the web page `http://{your host}/#/flows/{your flow name}/jobs`

## Run from Git events

Supported Git provider: [GitHub](https://github.com), [GitLab](https://gitlab.com), [Gogs](https://gogs.io/) 和 [Gitee](https://gitee.com/)

Supported Git events: `Push`, `Tag` 和 `Pull Request`

For how to config Git, please refer [Setup Git](en/git/index.md)