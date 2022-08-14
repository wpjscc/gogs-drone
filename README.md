
```
git clone https://github.com/wpjscc/gogs-drone
sudo docker-compose up
```

## 访问


gogs  http://127.0.0.1:3000

drone  http://127.0.0.1:8000

账号密码通用

## 安装 exec-pipes

[官网](https://docs.drone.io/pipeline/exec/overview/)

下面是 linux的可以直接用

```
mkdir /etc/drone-runner-exec
mkdir /var/log/drone-runner-exec

vi /etc/drone-runner-exec/config
DRONE_RPC_PROTO=http
DRONE_RPC_HOST=10.8.0.8:8000
DRONE_RPC_SECRET=gjO9kVnS7PdixaGF
DRONE_LOG_FILE=/var/log/drone-runner-exec/log.txt


./drone-runner-exec service install
./drone-runner-exec service start

# 验证安装成功
cat /var/log/drone-runner-exec/log.txt
```

## 使用

* 进入 http://127.0.0.1:3000    (gogs) 同步此仓库，https://github.com/wpjscc/gogs-drone-nginx
* 进入 http://127.0.0.1:8000   （drone）点击同步按钮，看到同步的项目后，进入点击活动项目
* 第一次需进入http://127.0.0.1:3000 ,找到项目，手动同步下webhook，后面就可以自动运行了
* 部署成功访问http://127.0.0.1:8080 (nginx)

## done