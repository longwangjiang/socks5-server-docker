# 搭建docker的sock5服务器

自己建立文件夹并，下载Dockerfile文件
```
wget https://raw.githubusercontent.com/longwangjiang/socks5-server-docker/master/Dockerfile
```
## 进入Dockerfile文件所在目录，制作带密码的镜像，USERNAME=你的用户名，PASSWD=你的密码

```
docker build --rm --no-cache -t sock5-server --build-arg USERNAME=shenyu --build-arg PASSWD=123456 .
```
## 进入Dockerfile文件所在目录，制作不带用户名密码的镜像
```
docker build --rm --no-cache -t sock5-server .
```
## 运行

```bash
docker run --restart unless-stopped --name sock5-server -p 1080:1080 -d sock5-server
```
## 别人做好的镜像直接pull也行
```
docker pull teamide/sock5-server:latest
```
然后
```
docker run --restart unless-stopped --name sock5-server -p 1080:1080 -d teamide/sock5-server
```
