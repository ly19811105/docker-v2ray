# V2Ray for Docker

## 概述

用于部署 V2Ray Websocket 容器的镜像。

## 镜像

 - DockerHub 的镜像：`billin9/v2ray`
 
## 运行

```shell
docker run -d --name v2ray \
    -p 8080:8080 \
    -e CONFIG_JSON='{"inbounds":[{"port":8080,"protocol":"vmess","settings":{"clients":[{"id":"933ef646-9ea8-e43f-46d2-035513f4dc39","alterId":69}]},"streamSettings":{"network":"ws","wsSettings":{"path":"/ws"}}}],"outbounds":[{"protocol":"freedom","settings":{}}]}' \
    billin9/v2ray
```

## 注意

V2Ray 将在部署时自动安装最新版本。

设定 ENV CONFIG_JSON 时，务必将配置文件的换行符 `\r\n` 变更为 `\n`，然后填入 ENV 。使用 Linux 的朋友可以忽略这一步。
