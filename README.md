## 介绍

由于换一次电脑就要重新安装多个开发环境的软件, 实在浪费时间
正好之前学习了 docker 和 docker-compose . 趁着最近有时间,
做了一个 一键启动 `mysql(5.7 & 8)` `redis` `mongoDB` 的
docker-compose 项目, 方便一键启动开发环境, 就不用每次去
百度, 安装, 解决错误

## 环境要求

1. [docker](https://docs.docker.com/get-docker/)
2. [docker-compose](https://docs.docker.com/compose/install/)

## 启动

```bash
git clone https://github.com/liaohui5/docker-dbs

cd docker-dbs

mkdir datas logs

cp example.env .env

docker-compose up -d
```

## 停止

```bash
docker-compose down
```

## 查看是否正常运行

```bash
docker-compose ps
```

## 连接测试

> 为什么要连接测试?

因为有可能把 .env 中的数据库链接密码之类的信息改了, 连接测试可以测试是否改成功了

如果没有安装对应的数据库客户端, 推荐使用 vscode 对应的数据库客户端插件来测试, 比较方便

但是如果你安装了 navicat, dataGrip 之类的, 直接用就行

- [MySQL](https://marketplace.visualstudio.com/items?itemName=formulahendry.vscode-mysql)

- [MongoDB for VS Code](https://marketplace.visualstudio.com/items?itemName=mongodb.mongodb-vscode)

- [vscode-redis-client](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-redis-client)

## 注意

默认启用的是 `mysql 5.7.*` 如果想要使用 mysql8 的话, 打开 docker-compose.yaml 的注释就好了
