# docker-haproxy-tomcat

## 克隆
```
git clone https://github.com/codeyu/docker-haproxy-tomcat.git

cd docker-haproxy-tomcat
```

## 启动

```
docker-compose up
```

## 停止

` Ctrl+C` 

or

`docker-compose stop` 

## 后台启动
```
docker-compose up -d
```

## 使用
访问 http://localhost:88 页面显示： 

**Hello, Docker.**

访问 HAProxy 统计 http://localhost:70/stats

用户名密码：`admin:password`