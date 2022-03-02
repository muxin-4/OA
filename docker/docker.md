<!-- https://www.imooc.com/wiki/emosweb/p1chapter3.html -->

#### docker 常用命令

![常用命令](./常用命令.png)

#### 创建 mysql 镜像

```
docker run -it -d --name emos-mysql -p 3307:3307 \
-m 500m -v /Users/wgy/ALL/config/dockerData/emos-mysql/mysql:/var/lib/mysql \
-v /Users/wgy/ALL/config/dockerData/emos-mysql/config:/etc/mysql/conf.d  \
-e MYSQL_ROOT_PASSWORD=2340666 \
-e TZ=Asia/Shanghai mysql:8.0.23 \
--lower_case_table_names=1
```

### 创建 MongoDB 镜像

<!-- https://www.jianshu.com/p/9e42f56c6b2d -->

#### 默认方式

docker run -itd --name emos-mongo -p 27017:27017 \
-v /Users/wgy/ALL/config/dockerData/emos-mongo:/etc/mongo -m 500m \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=abc123456 \
-e TZ=Asia/Shanghai \
mongo:4.4.7

todo 外部配置
mongodb.conf

### 创建 redis 镜像

#### 默认方式

```
docker run -it -d --name emos-redis -m 300m  -p 6379:6379 \
-e TZ=Asia/Shanghai \
-v /Users/wgy/ALL/config/dockerData/emos-redis:/usr/local/etc/redis redis:6.0.10 \
redis-server
```

#### 外部配置

mac 需要先下载 redis

```
brew install redis
```

```
docker run -it -d --name emos-redis -m 300m  -p 6379:6379 \
-e TZ=Asia/Shanghai \
-v /Users/wgy/ALL/config/dockerData/emos-redis/redis.conf:/usr/local/etc/redis.conf redis:6.0.10 \
redis-server /usr/local/etc/redis.conf

```

#### 创建 RabbitMQ 镜像

```
docker run -it -d --name emos-mq -m 300m \
-p 4369:4369 -p 5672:5672 -p 15672:15672 -p 25672:25672 \
-e TZ=Asia/Shanghai \
rabbitmq:3.8.9
```
