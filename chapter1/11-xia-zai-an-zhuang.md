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

打开浏览器，输入地址：http://localhost，访问页面，出现如下页面表示访问成功![](/assets/n13)

### 停止nginx

命令行进入nginx根目录，执行如下命令，停止服务器：

```
# 强制停止nginx服务器，如果有未处理的数据，丢弃
D:/resp_application/nginx-1.13.5> nginx -s stop

# 优雅的停止nginx服务器，如果有未处理的数据，等待处理完成之后停止
D:/resp_application/nginx-1.13.5> nginx -s quit
```

### 2. ubuntu安装



### 3. mac os安装





