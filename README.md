# Confluence

### 数据库设置

使用 MySQL 8.0

##### 创建DATABASE


```mysql
CREATE DATABASE confluence CHARACTER SET utf8mb4 COLLATE utf8mb4_bin;
```

##### 创建用户

```mysql
CREATE user 'confluence'@'%' IDENTIFIED BY '<password>';
```

##### 授权用户

```mysql
GRANT ALL PRIVILEGES ON confluence.* TO 'confluence'@'%' WITH GRANT OPTION;
```

### 2. Docker Compose

##### 运行

```bash
docker-compose up -d
```

##### 破解

```bash
// 进入容器环境
$ docker exec -it <ContainerID> bash
// 进入 atlassian-agent.jar 目录
$ cd /var/atlassian
// 生成key
$ java -jar atlassian-agent.jar -d -m test@test.com -n BAT -p 'conf' -o http://localhost:8090 -s <ServerID>
```

