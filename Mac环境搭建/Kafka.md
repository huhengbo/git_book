## Docker 安装Kafka
### 0x01 装前须知
	1. Kafka需要依赖Zookeepr
	2. Kafka现在没有官方源，所以现阶段只能选择第三方，或者自己写DockerFile
	3. 未完待续
### 0x02 安装
	1. 新建Docker-compose.yml 文件
	2. 录入下面数据
	
``` yaml
version: '2.1'
services:
  zookeeper:
    image: wurstmeister/zookeeper
    ports:
    	# 宿主:容器
      - 2181:2181
  kafka:
    image: wurstmeister/kafka
    ports:
      - 9092:9092
    environment:
    	# 宿主机IP
      KAFKA_ADVERTISED_HOST_NAME: 192.168.1.118
      KAFKA_ZOOKEEPER_CONNECT: zookeeper:2181
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
```

### 0x03 启动
	1. 单节点启动 docker-compose up -d
	2. 多节点启动 docker-compose scale kafka=3
### 0x04 注意事项
	1. 暴露端口信息。使用宿主：容器 （HOST:CONTAINER）格式或者仅仅指定容器的端口（宿主将会随机选择端口）都可以。

