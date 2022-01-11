# 任务缓存 (cache)

当并行执行时, 任务会运行在不同的 Agent 中。如果这时想访问同一数据，这时就需要配置缓存。

![cache demo](../../_images/job/cache_demo.png)

## 如何使用缓存

可以在 步骤 (step) 中使用 `cache`。配置缓存需要使用 `key` 来定义缓存名称，如果该步骤为 写入缓存，则需要配置 `paths` 指定那个路径或文件需要写入。

```yaml
steps:
  - name: write
    cache:
      key: mycache
      paths:
        - "./my_demo_cache"
    bash: |
      mkdir -p ./my_demo_cache
      echo "cache_content" > ./my_demo_cache/my_file

  - name: clean
    bash: |
      # 从本地工作区(workspace) 删除该目录, 确保之后的缓存从正确的位置读取
      rm -rf ./my_demo_cache

  - parallel:
      flow_1:
        docker:
          image: "ubuntu:21.04"
        steps:
        - name: read
          cache:
            key: mycache 
          bash: |
            cat ./my_demo_cache/my_file

      flow_2:
        docker:
          image: "ubuntu:18.04"
        steps:
        - name: read
          cache:
            key: mycache 
          bash: |
            cat ./my_demo_cache/my_file

```

运行结果如下:

![cache_run](../../_images/job/cache_run_example.png)