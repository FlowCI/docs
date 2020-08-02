# 插件

在 flow.ci 中配置插件非常简单，只需要在工作流 YAML 中配置插件名称即可, 例如: `gitclone` 插件

```yml
envs:
  FLOWCI_GIT_URL: "https://github.com/gin-gonic/gin.git"

steps:
  - name: clone
    plugin: 'gitclone'
```

插件列表，以及插件说明可以在工作流设置 `settings` -> `YAML` -> `plugins` 找到。

![list](../../src/plugins.png)
