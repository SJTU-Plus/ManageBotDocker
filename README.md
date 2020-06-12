# ManageBotDocker

[ManagerBot](https://github.com/SJTU-Plus/ManagerBot)和[ManagerBotServer](https://github.com/SJTU-Plus/ManagerBotServer)作为群管机器人的前后端，均可以单独按照各自项目的运行方法运行并且能够正常工作。

但是想使用docker进行部署，这里提供使用docker-compose同时管理2个项目的方法。

首先将两个项目下载到本地同一目录下，然后下载本repo中提供的`docker-compose.yml`文件。工程结构应该如下。

```
docker-compose.yml
qbot
  Dockerfile
  其他python文件
web
  Dockerfile
  其他python文件
```

然后修改`docker-compose.yml`文件中的3个service各自的`ENV`。其中web和qbot的相关环境变量在两个项目主页和代码中有介绍。

接着运行
```
docker-compose build  # 构建容器
docker-compose up -d  # 在后台运行容器
```

如果无错误信息，即正确配置。
