# 版本升级

### 从版本 1.22.xx 升级至 1.23.xx

由于数据库的改动，需要在 `mongodb` 中执行以下脚本，否则会服务启动失败

```bash
db.job.dropIndex('index_flow_id')
db.flow_yml.dropIndex('index_flow_id')
db.flow_yml.dropIndex('index_flow_id_and_yaml_name')
```
