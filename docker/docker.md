<!-- https://www.imooc.com/wiki/emosweb/p1chapter3.html -->
#### docker常用命令
![常用命令](./常用命令.png)



#### 创建mysql镜像
```
docker run -it -d --name emos-mysql -p 3307:3307 \
-m 500m -v /Users/wgy/ALL/config/dockerData/emos-mysql/mysql:/var/lib/mysql \
-v /Users/wgy/ALL/config/dockerData/emos-mysql/config:/etc/mysql/conf.d  \
-e MYSQL_ROOT_PASSWORD=2340666 \
-e TZ=Asia/Shanghai mysql:8.0.23 \
--lower_case_table_names=1
```

### 创建MongoDB镜像
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

### 创建redis镜像

#### 默认方式
docker run -it -d --name redis -m 300m  -p 6379:6379 \
-e TZ=Asia/Shanghai \
-v /Users/wgy/ALL/config/dockerData/emos-redis:/usr/local/etc/redis redis:6.0.10 \
redis-server

todo 外部配置


#### 创建RabbitMQ镜像


