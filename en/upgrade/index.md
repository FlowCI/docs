# Upgrade

### from version 1.22.xx to 1.23.xx

the database structure has been changed on version `1.23.xx`, need to execute the following script on the mongodb

```bash
db.job.dropIndex('index_flow_id')
db.flow_yml.dropIndex('index_flow_id')
db.flow_yml.dropIndex('index_flow_id_and_yaml_name')
```