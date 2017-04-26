# m1-docker
Magento 1x Docker Environment

## Magento Configuration
Unsecure Base URL: http://127.0.0.1:8080/

Secure Base URL: https://127.0.0.1/

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
