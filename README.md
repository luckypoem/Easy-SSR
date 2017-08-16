![][1]
**本脚本适用环境：**  
系统支持：CentOS，Debian，Ubuntu  
内存要求：≥128M  
SSR更新日期：2017 年 07 月 27 日  

**关于本脚本：**  
一键安装 ShadowsocksR 服务端。  
请下载与之配套的客户端程序来连接。    
（以下客户端只有 Windows 客户端和 Python 版客户端可以使用 SSR 新特性，其他原版客户端只能以兼容的方式连接 SSR 服务器）  

**默认配置：**  
服务器端口：自己设定（如不设定，默认为 2333）  
密码：自己设定（如不设定，默认为 lmeoo.com）  
加密方式：自己设定（如不设定，默认为 aes-256-cfb）  
协议（Protocol）：自己设定（如不设定，默认为 origin）  
混淆（obfs）：自己设定（如不设定，默认为 plain）  

**客户端下载：**  
[Windows][2] / [Android][3]

使用方法：  
使用root用户登录，运行以下命令：

``` vim
wget --no-check-certificate https://raw.githubusercontent.com/Moexin/Easy-SSR/master/shadowsocksR.sh && chmod +x shadowsocksR.sh && ./shadowsocksR.sh 2>&1 | tee shadowsocksR.log
```
安装完成后，脚本提示如下：

``` oxygene
Congratulations, ShadowsocksR server install completed!
Your Server IP        :your_server_ip
Your Server Port      :your_server_port
Your Password         :your_password
Your Protocol         :your_protocol
Your obfs             :your_obfs
Your Encryption Method:your_encryption_method

Welcome to visit:http://lmeoo.com/easy-ssr一键完成shadowsocksr安装.html
Enjoy it!
```
**卸载方法：**
使用 root 用户登录，运行以下命令：
``` stylus
./shadowsocksR.sh uninstall
```
安装完成后即已后台启动 ShadowsocksR ，运行：

``` maxima
/etc/init.d/shadowsocks status
```
可以查看 ShadowsocksR 进程是否已经启动。  
本脚本安装完成后，已将 ShadowsocksR 自动加入开机自启动。

**使用命令：**  
启动：`/etc/init.d/shadowsocks start`  
停止：`/etc/init.d/shadowsocks stop`  
重启：`/etc/init.d/shadowsocks restart`  
状态：`/etc/init.d/shadowsocks status`  

配置文件路径：`/etc/shadowsocks.json`  
日志文件路径：`/var/log/shadowsocks.log`  
代码安装目录：`/usr/local/shadowsocks`  

**多用户配置示例：**

``` json
{
"server":"0.0.0.0",
"server_ipv6": "[::]",
"local_address":"127.0.0.1",
"local_port":1080,
"port_password":{
    "8989":"password1",
    "8990":"password2"，
    "8991":"password3"
},
"timeout":300,
"method":"aes-256-cfb",
"protocol": "origin",
"protocol_param": "",
"obfs": "plain",
"obfs_param": "",
"redirect": "",
"dns_ipv6": false,
"fast_open": false,
"workers": 1
}
```
**可选加密方式：**

``` lsl
none
aes-256-cfb
aes-192-cfb
aes-128-cfb
aes-256-cfb8
aes-192-cfb8
aes-128-cfb8
aes-256-ctr
aes-192-ctr
aes-128-ctr
chacha20-ietf
chacha20
rc4-md5
rc4-md5-6
```
**可选协议：**

``` smali
origin
verify_deflate
auth_sha1_v4
auth_sha1_v4_compatible
auth_aes128_md5
auth_aes128_sha1
auth_chain_a
auth_chain_b
```
**可选混淆：**

``` lsl
plain
http_simple
http_simple_compatible
http_post
http_post_compatible
tls1.2_ticket_auth
tls1.2_ticket_auth_compatible
tls1.2_ticket_fastauth
tls1.2_ticket_fastauth_compatible
```


  [1]: http://imglf.nosdn.127.net/img/cEczVHlUNlVvWHpQS3BqamozeGRxaXY1eXJueFBnQks2OXQvNHFPTXFhOWtySDJYWjN2TGRRPT0.png
  [2]: https://raw.githubusercontent.com/Moexin/Easy-SSR/master/ShadowsocksR-4.7.0-win.7z
  [3]: https://raw.githubusercontent.com/Moexin/Easy-SSR/master/ssr_3.4.0.6.apk