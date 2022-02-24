# 搭建docker的sock5服务器

## 制作带密码的镜像，USERNAME=你的用户名，PASSWD=你的密码

```
docker build --rm --no-cache -t sock5-server --build-arg USERNAME=shenyu --build-arg PASSWD=123456 .
```
## 制作不带用户名密码的镜像
```
docker build --rm --no-cache -t sock5-server .
```
## 运行

```bash
docker run --restart unless-stopped --name sock5-server -p 1080:1080 -d sock5-server
```
