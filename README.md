# ManageBotDocker

[ManagerBot](https://github.com/SJTU-Plus/ManagerBot)群管机器人可以按照项目中的运行方法运行并且能够正常工作，也可以和COOLQ、redis部署到一起。

这里提供使用docker-compose同时管理几个容器的方法。

首先将[ManagerBot](https://github.com/SJTU-Plus/ManagerBot)下载到本地，然后下载本repo中提供的`docker-compose.yml`文件。工程结构应该如下。

```
docker-compose.yml
qbot
  Dockerfile
  其他python文件
```

然后修改`docker-compose.yml`文件中的3个service各自的`ENV`。其中qbot的相关环境变量在项目主页和代码中有介绍。

接着运行
```
docker-compose build  # 构建容器
docker-compose up -d  # 在后台运行容器
```

然后访问9000端口登录酷Q，默认密码为`MAX8char`。

如果无错误信息，即正确配置。
