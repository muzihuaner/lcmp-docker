# 原版地址

https://github.com/lhuang001/lcmp-docker


## 修改描述

若自行部署mysql或使用第三方数据库，则不需要再另行安装mysql


# 使用教程
1. 拉取

```
git clone https://github.com/codionx/lcmp-docker.git
mv lcmp-docker web
cd web
```

2. 创建docker-compose、env、caddy配置文件

```
cp docker-compose.yml.sample  docker-compose.yml
cp .env.sample .env
cp services/caddy/etc/caddy/Caddyfile.sample services/caddy/etc/caddy/Caddyfile
```

3. 在项目目录启动

```
docker-compose up -d
```

4. 上传代码到项目目录www目录下

5. 在项目根目录执行chown -R 1000:1000 www, 避免php程序没有对应权限
6. 修改services/caddy/etc/caddy/Caddyfile文件，配置caddy代理


## 注意事项：
1. www下文件权限为644，文件夹权限为755.请勿使用777，这会带来安全风险
