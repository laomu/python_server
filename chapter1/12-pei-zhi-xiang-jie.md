# nginx配置

nginx是一个功能非常强大的web服务器加反向代理服务器，同时又是邮件服务器等等

在项目使用中，使用最多的三个核心功能是反向代理、负载均衡和静态服务器

这三个不同的功能的使用，都跟nginx的配置密切相关，nginx服务器的配置信息主要集中在nginx.conf这个配置文件中，并且所有的可配置选项大致分为以下几个部分

```python
main                                # 全局配置

events {                            # nginx工作模式配置

}

http {                                # http设置
    ....
    
    server {                        # 服务器主机配置
        ....
        location {                    # 路由配置
            ....
        }
        
        location path {
            ....
        }
        
        location otherpath {
            ....
        }
    }
    
    server {
        ....
        
        location {
            ....
        }
    }
    
    upstream name {                    # 负载均衡配置
        ....
    }
}
```

如上述配置文件所示，主要由6个部分组成：

1. main：用于进行nginx全局信息的配置
2. events：用于nginx工作模式的配置
3. http：用于进行http协议信息的一些配置
4. server：用于进行服务器访问信息的配置
5. location：用于进行访问路由的配置
6. upstream：用于进行负载均衡的配置

### main模块

观察下面的配置代码

```
# user nobody nobody;
worker_processes 2;
# error_log logs/error.log
# error_log logs/error.log notice
# error_log logs/error.log info
# pid logs/nginx.pid
worker_rlimit_nofile 1024;
```

上述配置都是存放在main全局配置模块中的配置项

* user用来指定nginx worker进程运行用户以及用户组，默认nobody账号运行
* worker\_processes指定nginx要开启的子进程数量，运行过程中监控每个进程消耗内存\(一般几M~几十M不等\)根据实际情况进行调整，通常数量是CPU内核数量的整数倍
* error\_log定义错误日志文件的位置及输出级别【debug / info / notice / warn / error / crit】
* pid用来指定进程id的存储文件的位置
* worker_rlimit_nofile用于指定一个进程可以打开最多文件数量的描述



### event 模块

上干货

```
event {
    worker_connections 1024;
    multi_accept on;
    use epoll;
}
```

上述配置是针对nginx服务器的工作模式的一些操作配置

* worker\_connections 指定最大可以同时接收的连接数量，这里一定要注意，最大连接数量是和worker processes共同决定的。
* multi\_accept 配置指定nginx在收到一个新连接通知后尽可能多的接受更多的连接
* use epoll 配置指定了线程轮询的方法，如果是linux2.6+，使用epoll，如果是BSD如Mac请使用Kqueue



### http模块

作为web服务器，http模块是nginx最核心的一个模块，配置项也是比较多的

```

```







