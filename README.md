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
  
## Docker Shell Access
  ```bash
  docker exec -it <containerIdOrName> bash
  ```
