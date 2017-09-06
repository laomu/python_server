# Nginx安装

### 1. windows安装

官方网站下载地址：

```
https://nginx.org/en/download.html
```

如下图所示，下载对应的版本的nginx压缩包，解压到自己电脑上存放软件的文件夹中即可![](/assets/n12)解压完成后，文件目录结构如下：

![](/assets/n14)

### 启动nginx

1） 直接双击该目录下的nginx.exe，即可启动nginx服务器

2） 命令行计入该文件夹，执行nginx命令，也会直接启动nginx服务器

```
D:/resp_application/nginx-1.13.5> nginx
```

### 访问nginx

打开浏览器，输入地址：[http://localhost，访问页面，出现如下页面表示访问成功!\[\]\(/assets/n13](http://localhost，访问页面，出现如下页面表示访问成功![]%28/assets/n13)\)

### 停止nginx

命令行进入nginx根目录，执行如下命令，停止服务器：

```
# 强制停止nginx服务器，如果有未处理的数据，丢弃
D:/resp_application/nginx-1.13.5> nginx -s stop

# 优雅的停止nginx服务器，如果有未处理的数据，等待处理完成之后停止
D:/resp_application/nginx-1.13.5> nginx -s quit
```

### 2. ubuntu安装

按照正常软件的安装方式，直接通过如下命令进行安装：

```
$ sudo apt-get install nginx
```

![](/assets/n15)

安装完成即可，在/usr/sbin/目录下是nginx命令所在目录，在/etc/nginx/目录下是nginx所有的配置文件，用于配置nginx服务器以及负载均衡等信息

##### 查看nginx进程是否启动

```
$ ps -ef|grep nginx
```

nginx会自动根据当前主机的CPU的内核数目创建对应的进程数量\(当前ubuntu主机是2核4线程配置\)

![](/assets/n16)

##### 启动nginx服务器命令

直接执行nginx会按照默认的配置文件进行服务器的启动

```
$ nginx
```

![](/assets/n17)

##### 停止nginx服务命令

和windows系统执行过程一样，两种停止方式

```
$ nginx -s stop
or
$ nginx -s quit
```

![](/assets/n18)

##### 重新启动加载

同样也可以使用命令reopen和reload来重新启动nginx或者重新加载配合着文件。

### 3. mac os安装

直接通过brew进行nginx的安装，或者下载tar.gz压缩包都是可以的。

直接通过brew进行安装

```
brew install nginx
```

安装完成后，后续的命令操作，服务器的启动、进程查看、服务器的停止、服务器的重启已经文件加载命令都是一致的。

