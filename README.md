# 原版地址

https://github.com/lhuang001/lcmp-docker


## 修改描述

若自行部署mysql或使用第三方数据库，则不需要再另行安装mysql


# 使用教程
**1. 拉取**

```
git clone https://github.com/codionx/lcmp-docker.git
mv lcmp-docker web
cd web
```

**2. 创建docker-compose、env、caddy配置文件**

```
cp docker-compose.yml.sample  docker-compose.yml
cp .env.sample .env
cp services/caddy/etc/caddy/Caddyfile.sample services/caddy/etc/caddy/Caddyfile
```

**3. 修改Caddyfile文件，配置caddy代理**
```
nano /root/web/services/caddy/etc/caddy/Caddyfile
```

#### 网站示例：
PHP
```
hellobitch.com {
        root * /srv/hellobitch.com
        encode gzip
        file_server
        php_fastcgi php:9000
}
```
静态
```
hellobitch.com {
        root * /srv/hellobitch.com
        encode gzip
        file_server
}
```
反代
```
hellobitch.com {
        reverse_proxy http://you.are.bitch
}
```

**4. 上传代码到`~/web/www/`目录下**

**5. 在`~/web/`目录授权, 避免php程序没有对应权限**
```
chown -R 1000:1000 www
```
**6. 在项目目录启动**

```
docker-compose up -d
```

## 注意事项：
**1. www下文件权限为644，文件夹权限为755.请勿使用777，这会带来安全风险**
