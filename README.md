# m1-docker
Magento 1x Docker Environment

## Managing Docker Environment
### Start
  ```bash
  docker-compose up -d
  ```
### Stop
  ```bash
 docker-compose down
  ```
### Build/Rebuild
If you make changes to a DockerFile, you will need to rebuild the images to see the changes.
  ```bash
  docker-compose build && docker-compose up -d
  ```
### Shell Access
List the containers running to find the container's id or name that you want to connect to
  ```bash
  docker ps
  ```
Run the following command to get shell access to the specified container
  ```bash
  docker exec -it <containerIdOrName> bash
  ```
## MySQL Connectivity
When running, the MySQL container's port 3306 is bound to the host's (Your computer) port 3306. It's as if you are running MySQL on your computer (but it's really running inside the container). If you already have your own MySQL running (MAMP, WAMP, Custom MySQL Installation) over port 3306, you will need to update the *docker-compose.yml* to bind the MySQL container to a different port on your computer. Connect via your favorite MySQL editor, such as [Sequal Pro](https://sequelpro.com/)

| Key          | Value     |
| ------------ | --------- |
| **Host**     | 127.0.0.1 |
| **Port**     | 3306      |
| **Username** | project   |
| **Password** | project   |
| **Database** | project   |

## Magento Configuration
In the *app/etc/local.xml* file, the values shown below should be used to successfully connect to the database:
```xml
<config>
    <global>
        <resources>
            <default_setup>
                <connection>
                    ...
                    <host><![CDATA[mysql]]></host>
                    <username><![CDATA[project]]></username>
                    <password><![CDATA[project]]></password>
                    <dbname><![CDATA[project]]></dbname>
                    ...
                </connection>
            </default_setup>
        </resources>
    </global>
</config>
```

In the *core_config_data* table:

| Path                  | Value                  |
| --------------------- | ---------------------- |
| web/unsecure/base_url | http://127.0.0.1:8080/ |
| web/secure/base_url   | https://127.0.0.1/     |

## XDebug Configuration
To run xdebug, drop a *.user.ini* file into the magento root with the following contents:

```dosini
[xdebug]
xdebug.remote_enable=1
xdebug.remote_host=<YOUR-IP-ADDRESS>
```
