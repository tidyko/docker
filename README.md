# docker

* 下载hub.docker.com的官方镜像
```shell
docker pull <镜像名称:版本号>
```
* 如：
```shell
docker pull centos:latest
```

* 查看本机所有的docker镜像
```shell
docker images
```

* 运行一个docker镜像，生成对应容器
```shell
docker run
````

* 例如运行一个后台运行的centos：
```shell
docker run -d -it --name centos_latest centos:latest
```

* 运行一个后台运行的nginx docker镜像，并指定映射端口
```shell
docker run -d -p 8080:8080 nginx
```

* 运行一个后台运行的nginx docker镜像，并随机指定映射端口
```shell
docker run -d -P nginx
```

* 进入centos终端
```shell
docker attach centos_latest
```

* 退出但不中止centos终端
```shell
ctrl+p+q
```

* 查看所有处于运行状态的容器
```shell
docker ps
```

* 查看处于中止状态的容器
```shell
docker ps -a
```

* 清理所有处于终止状态的容器
```shell
docker container prune
```

* 停止一个后台运行的nginx docker容器
```shell
docker stop 容器id
```

* 删除一个停止运行的nginx docker容器
```shell
docker rm 容器id
```

* 删除一个镜像
```shell
docker rmi 镜像名称
```

* 执行Dockerfile，新建一个docker镜像
```shell
docker build -t 镜像名称:镜像版本 Dockerfile上下文
```
* 如：
```shell
docker build -t centos:chinese .
```

