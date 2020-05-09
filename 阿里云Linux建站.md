# linux

## 安装软件apt-get

* apt update 更新软件源
* apt install default jre安装jre

## ssh客户端上传文件到linux

```shell
scp /path/filename username@servername:/path/
```

## 登陆阿里云

* 运行bash
* ssh root@119.23.241.185 

## 运行java命令

```shell
nohup java -jar xxx.jar &
```

* nohup 一直运行，即使关闭终端
* & 后台运行，关闭终端后，程序也会关闭
* 联合起来用，表示关闭终端后台运行，会打印日志到nohup.out中

```shell
ps -ef 查看正在运行程序
kill -9 pid 杀死进程
```

## mariaDB

* 启动服务
  service mysql start
* 关闭服务
  service mysql stop
