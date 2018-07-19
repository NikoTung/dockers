## Apollo Docker-compose

This a all in one compose file about [Apollo](https://github.com/ctripcorp/apollo). The configservice ,adminservice and portal communicate through the docker network ,used to deploy on a single machine. It use the [Docker enviroment file](https://docs.docker.com/compose/env-file/) to manage the env, so all the datasources and meta server url can be set in runtime.



#### How to use

* clean build the project only with spring profile
* docker build the configservice ,adminservice and portal, the directory: config, admin and portal contain the official Dockerfile
* create your own `.env` file under the same directory of docker-compose.yml
* docker-compose up -d
* check the meta server http://yourip:18080
* check the port http://yourip:18087

#### env variables

* TAG: the release tag of apollo
* JAVA_OPTS: java options
* config_db_url: the configservice database url
* config_db_user: user of the configservice database 
* config_db_pwd: password of configservice user
* portal_db_url: the portal database url
* portal_db_user: user of the portal database 
* portal_db_pwd: password of portal user
* dev_meta: meta server url check the official [document](https://github.com/ctripcorp/apollo/wiki/%E5%88%86%E5%B8%83%E5%BC%8F%E9%83%A8%E7%BD%B2%E6%8C%87%E5%8D%97#23-%E9%85%8D%E7%BD%AE%E5%90%84%E7%8E%AF%E5%A2%83meta-service%E5%9C%B0%E5%9D%80)
* fat_meta: meta server url check the official [document](https://github.com/ctripcorp/apollo/wiki/%E5%88%86%E5%B8%83%E5%BC%8F%E9%83%A8%E7%BD%B2%E6%8C%87%E5%8D%97#23-%E9%85%8D%E7%BD%AE%E5%90%84%E7%8E%AF%E5%A2%83meta-service%E5%9C%B0%E5%9D%80)
* uat_meta: meta server url check the official [document](https://github.com/ctripcorp/apollo/wiki/%E5%88%86%E5%B8%83%E5%BC%8F%E9%83%A8%E7%BD%B2%E6%8C%87%E5%8D%97#23-%E9%85%8D%E7%BD%AE%E5%90%84%E7%8E%AF%E5%A2%83meta-service%E5%9C%B0%E5%9D%80)
* pro_meta: meta server url check the official [document](https://github.com/ctripcorp/apollo/wiki/%E5%88%86%E5%B8%83%E5%BC%8F%E9%83%A8%E7%BD%B2%E6%8C%87%E5%8D%97#23-%E9%85%8D%E7%BD%AE%E5%90%84%E7%8E%AF%E5%A2%83meta-service%E5%9C%B0%E5%9D%80)
