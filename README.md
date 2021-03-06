# ManageBotDocker

[ManagerBot](https://github.com/SJTU-Plus/ManagerBot)群管机器人可以按照项目中的运行方法运行并且能够正常工作，也可以和[ManagerBotServer](https://github.com/SJTU-Plus/ManagerBotServer)一起使用docker-compose统一管理。

这里提供使用docker-compose同时管理几个容器的方法。

1. 首先将本项目下载到本地，然后下载对应项目到对应目录。

  ```bash
  git clone https://github.com/Mrs4s/go-cqhttp go-cqhttp
  git clone https://github.com/SJTU-Plus/ManagerBot qbot
  git clone https://github.com/SJTU-Plus/ManagerBotServer web
  git clone https://github.com/SJTU-Plus/GroupPlus group-plus
  ```

  得到目录结构如下：

  ```
  docker-compose.yml
  web
    Dockerfile
    ...
  qbot
    Dockerfile
    ...
  GroupPlus
    Dockerfile
    ...
  go-cqhttp
    Dockerfile
    ...
  go-cqhttp-data
    ...
  ```

2. 修改`docker-compose.yml`文件中的`ATTESTATION_SECRET`。
3. 按照[ManagerBotServer](https://github.com/SJTU-Plus/ManagerBotServer)中的内容新建并修改`web/config.json`。
4. 修改 Dockerfile 中的环境变量。
5. 运行`docker-compose build`构建容器。
6. 运行`docker-compose run go-cqhttp`进行初始化。第一次运行时将生成`config.json`和`device.json`，按照[go-cqhttp](https://github.com/Mrs4s/go-cqhttp/blob/master/docs/config.md)的方法配置`go-cqhttp-data/config.json`。第二次运行时，可能需要手动输入验证码或者访问链接并扫描二维码通过QQ安全检查，此时请按提示进行操作。第三次运行时应该正常，此时表示初始化完成。
7. 最后运行

```
docker-compose up # 运行容器
或者
docker-compose up -d  # 在后台运行容器
```

如果无错误信息，即正确配置。
