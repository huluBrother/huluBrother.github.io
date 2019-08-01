# Nginx 安装部署
# 1 安装编译工具及库文件

```
yum -y install make zlib zlib-devel gcc-c++ libtool  openssl openssl-devel
```

# 安装PCRE

> PCRE 作用是让 Nginx 支持 Rewrite 功能。

```
cd /usr/local/src/              # 切换到下载目录
wget http://downloads.sourceforge.net/project/pcre/pcre/8.35/pcre-8.35.tar.gz # 下载内容
tar zxvf pcre-8.35.tar.gz # 解压命令
cd pcre-8.35 #进入安装包目录
./configure
make && make install  # 编译安装
pcre-config --version # 查看版本，验证安装是否成功
```

# 安装nginx

```
cd /usr/local/src/  # 创建安装目录
wget http://nginx.org/download/nginx-1.6.2.tar.gz  # 下载安装包
tar zxvf nginx-1.6.2.tar.gz             # 解压
cd nginx-1.6.2                          # 进入安装目录
./configure --prefix=/usr/local/src/nginx --with-http_stub_status_module --with-http_ssl_module --with-pcre=/usr/local/src/pcre-8.35
make && make install                               # 编译安装
/usr/local/nginx/sbin/nginx -v   # 查看nginx版本
/usr/local/nginx/sbin/nginx -t   # 检查配置文件nginx.conf的
```

# 启动维护Nginx

```
/usr/local/nginx/sbin/nginx                        # 启动
/usr/local/nginx/sbin/nginx -s reload            # 重新载入配置文件
/usr/local/nginx/sbin/nginx -s reopen            # 重启 Nginx
/usr/local/nginx/sbin/nginx -s stop              # 停止 Nginx
