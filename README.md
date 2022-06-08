# 原版地址

https://github.com/lhuang001/lcmp-docker


## 修改描述

若自行部署mysql或使用第三方数据库，则不需要再另行安装mysql


# 使用教程
1. 拉取

```
git clone https://github.com/codionx/lcmp-docker.git
```
```
mv lcmp-docker web
```
```
cd web
```

2. 修改docker-compose配置

```
cp docker-compose.yml.sample  docker-compose.yml
```

3. 修改env

```
cp .env.sample .env
```

4. 修改caddy配置文件

```
cp services/caddy/etc/caddy/Caddyfile.sample services/caddy/etc/caddy/Caddyfile
```

5. 切换到项目根目录，docker-compose up -d启动项目
6. 上传代码到www目录下
7. 在根目录执行chown -R 1000:1000 www, 避免php程序没有对应权限
8. 修改services/caddy/etc/caddy/Caddyfile文件，配置caddy代理


## 注意事项：
1. www下文件权限为644，文件夹权限为755.请勿使用777，这会带来安全风险
