# 使用 Docker 部署 PasteMe

<!-- 若要使用 Nginx 和 systemd 部署请移步：[朴素部署](deploy/directly/) -->

## 部署

下载 [PasteMe/docker-compose.yml][docker-compose.yml]，然后执行 `docker-compose up -d`

```bash
wget https://cdn.jsdelivr.net/gh/LucienShui/PasteMe@main/docker-compose.yml
docker-compose up -d
```

命令执行完成后等待 `30s`（因为需要初始化数据库和等待 `healthy check`），然后运行 `docker ps -a`，当看到所有的容器的状态没有 `unhealthy` 或 `Exited (x) xxx` 就代表 PasteMe 已经启动成功

## 更新

```bash
docker-compose pull
docker-compose up -d
```

## 文件夹介绍

第一次执行完 `docker-compose up -d` 之后，会出现一个名为 `data` 的文件夹，其中有四个文件夹。

| 文件夹名 | 备注 |
| --- | --- |
| `backend-config` | 后端的配置文件 |
| `frontend-user` | 前端的配置文件和用户文件 |
| `nginx-logs` | 前端 Nginx 的日志文件 |
| `mysql` | MySQL 的持久化文件 |

## 日志

+ 前端 `Nginx` 日志位于 `data/nginx-logs` 下
+ 后端日志通过 `docker logs pasteme-backend` 查看
+ 数据库日志通过 `docker logs pasteme-mysql` 查看

## 鸣谢

[OnlineJudgeDeploy](https://github.com/QingdaoU/OnlineJudgeDeploy)

[docker-compose.yml]: https://cdn.jsdelivr.net/gh/LucienShui/PasteMe@main/docker-compose.yml
