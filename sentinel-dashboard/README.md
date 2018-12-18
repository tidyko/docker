* 1.进入build目录执行
```shell
docker build -t sentinel-dashboard:1.4.0 .
```

* 2.在当前目录下执行
```shell
docker-compose -f docker-compose.yml up
```

* 3.后续启动通过docker start container_id或者docker start image_id启动
