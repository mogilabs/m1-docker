# m1-docker
Magento 1x Docker Environment

## Starting The Environment
  ```bash
  docker-compose up -d
  ```
## Stopping The Environment
  ```bash
 docker-compose down
  ```
## Rebuilding The Environment
If you make changes to a DockerFile, you will need to rebuild the images to see the changes.
  ```bash
  docker-compose build
  ```
## Container Shell Access
List the containers running to find the container's id or name that you want to connect to
  ```bash
  docker ps
  ```
Run the following command to get shell access to the specified container
  ```bash
  docker exec -it <containerIdOrName> bash
  ```
## Connecting to MySQL
Port 3306 is bound to the host's (Your computer) port 3306. Because of this you can connect to MySQL via 127.0.0.1:3306.

| Key          | Value     |
| ------------ | --------- |
| **Host**     | 127.0.0.1 |
| **Username** | project   |
| **Password** | project   |
| **Database** | project   |

## Magento Configuration
In the *core_config_data* table:

| Path                  | Value                  |
| --------------------- | ---------------------- |
| web/unsecure/base_url | http://127.0.0.1:8080/ |
| web/secure/base_url   | https://127.0.0.1/     |
