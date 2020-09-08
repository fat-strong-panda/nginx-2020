nginx

##### 1、基本概念

- nginx是什么，做什么事情

*Nginx* (engine x) 是一个高性能的[HTTP](https://baike.baidu.com/item/HTTP)和[反向代理](https://baike.baidu.com/item/反向代理/7793488)web服务器，其特点是占有内存少，[并发](https://baike.baidu.com/item/并发/11024806)能力强，能够支持高达 50,000 个并发连接数的响应。事实上nginx的并发能力在同类型的网页服务器中表现较好，中国大陆使用nginx网站用户有：百度、[京东](https://baike.baidu.com/item/京东/210931)、[新浪](https://baike.baidu.com/item/新浪/125692)、[网易](https://baike.baidu.com/item/网易/185754)、[腾讯](https://baike.baidu.com/item/腾讯/112204)、[淘宝](https://baike.baidu.com/item/淘宝/145661)等。

nginx可以处理静态文件、负载均衡、反向代理、动静分离等。

- 反向代理概念

正向代理：是一个位于客户端和原始服务器(origin server)之间的服务器，为了从原始服务器取得内容，客户端向代理发送一个请求并指定目标(原始服务器)，然后代理向原始服务器转交请求并将获得的内容返回给客户端。客户端才能使用正向代理。需要在客户端中配置代理服务器。

反向代理：反向代理服务器位于用户与目标服务器之间，但是对于用户而言，反向代理服务器就相当于目标服务器，即用户直接访问反向代理服务器就可以获得目标服务器的资源。同时，用户不需要知道目标服务器的地址，也无须在用户端作任何设定。反向代理服务器通常可用来作为Web加速，即使用反向代理作为Web服务器的前置机来降低网络和服务器的负载，提高访问效率。

- 负载均衡概念

负载均衡，英文名称为Load Balance，其含义就是指将负载（工作任务）进行平衡、分摊到多个操作单元上进行运行，例如FTP服务器、Web服务器、企业核心应用服务器和其它主要任务服务器等，从而协同完成工作任务。

负载均衡构建在原有网络结构之上，它提供了一种透明且廉价有效的方法扩展服务器和网络设备的带宽、加强网络数据处理能力、增加吞吐量、提高网络的可用性和灵活性。

- 动静分离概念

动静分离是指在web服务器架构中，将静态页面与动态页面或者静态内容接口和动态内容接口分开不同系统访问的架构设计方法，进而提升整个服务访问性能和可维护性。

例如：html、css、js等静态资源部署在静态资源服务器中，jsp、servlet等动态资源部署在tomcat服务器中，客户端需要静态资源的时候，nginx就转发到静态资源服务器，需要动态资源的时候，nginx就转发到tomcat服务器，这样就实现了动静分离。





##### 2、nginx下载安装、常用命令和配置文件

- 在linux系统中安装nginx

nginx下载地址：http://nginx.org/en/download.html

nginx 相关依赖安装

yum install gcc-c++

pcre安装：yum install -y pcre pcre-devel

zlib安装：yum install -y zlib zlib-devel

openssl安装：yum install -y openssl openssl-devel

yum -y install make zlib zlib-devel gcc-c++ libtool   openssl openssl-devel

wget http://nginx.org/download/nginx-1.15.9.tar.gz

tar -zxvf nginx-1.15.9.tar.gz

mkdir nginx

./configure --prefix=/usr/local/nginx/ --with-http_ssl_module --with-http_stub_status_module 

make && make install

启动nginx ：进入sbin     ./nginx

输入ip可以访问

如果访问不到就先查看linux开放的端口 firewall-cmd --list-all

设置开放端口：

关闭防火墙：systemctl stop firewalld

- nginx常用命令
- nginx配置文件



3、nginx配置实例(反向代理)

4、nginx配置实例(负载均衡)

5、nginx配置实例(动静分离)

6、nginx配置高可用集群

7、nginx原理