# Environment with Docker

Agent could use Docker to support any runtime environments, it could be set from `docker` or `dockers` in the YAML configuration.

> Docker installation is needed from Agent

## Use Docker

To use Docker environment, the only thing you need to do is apply `docker` from YAML.

After this kind of setup, the script defined in `bash` will be run within the docker container.


- `docker` within `step`

  Example: the bash script will be executed within `openjdk:11` or `openjdk:8`
 
    ```yaml
    steps:
    - name: step_1
      docker:
        image: "openjdk:11"
      bash: "Run from openjdk 11"

    - name: step_2
      docker:
        image: "openjdk:8"
      bash: "Run from openjdk 8"
    ```

### Apply `docker` from Flow

All the steps will apply the `docker` defined from Flow level.

The step level `docker` will be applied as top priority.

```yaml
docker:
  image: "openjdk:11"

steps:
- name: step_1
  bash: "Run from openjdk 11"

- name: step_2
  docker:
   image: "openjdk:8"
  bash: "Run from openjdk 8"

```

## Use multiple Docker images

The `dockers` could be used for when multiple services like `redis`, `mongodb` and others are need in a step. 

The `is_runtime` must be defined for bash script environment.

The `wait-for-it.sh` is built-in script in Agent, you could use it to wait for service until it's running.

__Example__: Use `mysql` service in the step

```yaml
steps:
- name: run mutiple dockers
  dockers:
    - image: ubuntu:21.04
      is_runtime: true # the bash script runs in this image
      
    - image: mysql:5.6
      environment:
        MYSQL_ROOT_PASSWORD: 12345
  bash: |
    ## Get container id
    echo "ubuntu:21.04 id = $CONTAINER_ID_0"
    echo "mysql:5.6 id    = $CONTAINER_ID_1"

    ## Get container IP address, the default network mode is 'bridge'
    echo "ubuntu:21.04 ip = $CONTAINER_IP_0"
    echo "mysql:5.6 ip    = $CONTAINER_IP_1"

    ## Built-in wait-for-it.sh, wait 'mysql' service
    wait-for-it.sh ${CONTAINER_IP_1}:3306 -t 30
    if [ $? == 0 ];then
      docker run --network ${FLOWCI_AGENT_DOCKER_NETWORK} --rm mysql:5.6 mysql -h${CONTAINER_IP_1} -uroot -p12345 mysql -e "select * from user"
    fi
```