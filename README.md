# shadowsocks

## How to install on Ubuntu

```bash
# apt-get update && apt-get install -y python-pip && pip install --upgrade pip && apt-get install -y git
 
# pip install git+https://github.com/shadowsocks/shadowsocks.git@master
 
# apt-get install build-essential && wget https://github.com/jedisct1/libsodium/releases/download/1.0.8/libsodium-1.0.8.tar.gz && tar xf libsodium-1.0.8.tar.gz && cd libsodium-1.0.8 && ./configure && make -j2 && make install && ldconfig && touch /etc/shadowsocks.json && echo '{"server":"::", "server_port":8388, "local_address": "127.0.0.1", "local_port":1080, "password":"xxxx", "timeout":300, "method":"chacha20", "fast_open": false }' > /etc/shadowsocks.json && ssserver -c /etc/shadowsocks.json -d start
```

## How to install on Windows

1. download a installation package from [shadowsocks/libQtShadowsocks](https://github.com/shadowsocks/libQtShadowsocks/releases), e.g., [shadowsocks-libqss-v2.0.2-win64.7z](https://github.com/shadowsocks/libQtShadowsocks/releases/download/v2.0.2/shadowsocks-libqss-v2.0.2-win64.7z), and extract it
2. create a configuration file named ```config.json``` in the folder where the .exe file is, and add the following into the ```config.json```:

```json
{  
    "server":"0.0.0.0",  
    "server_port":8023,  
    "password":"wyvbboy",  
    "timeout":600,  
    "method":"aes-256-cfb",  
    "http_proxy": false,  
    "auth": false  
}
```
3. create a start shell named ```shadowsocks-server.bat```, and add the following into this file:
```
@echo off
if "%1" == "h" goto begin 
	mshta vbscript:createobject("wscript.shell").run("%~nx0 h",0)(window.close)&&exit
:begin 
shadowsocks-libqss.exe -c config.json -S
```
4. double click the ```.bat``` file, then shadowsocks will run in background.

## References

1. [DigitalOcean搭建Shadowsocks](https://blog.csdn.net/bleachswh/article/details/73896348)

2. [升级pip后出现ImportError: cannot import name main](https://blog.csdn.net/accumulate_zhang/article/details/80269313)

3. [查看IP地址](https://whoer.net/zh)

4. [ip111](http://ip111.cn/)

5. [shadowsocks-windows](https://github.com/shadowsocks/shadowsocks-windows/releases)

6. [other shadowsocks client](https://shadowsocks.org/en/download/clients.html)

7. [在Windows Server 上搭建Shadowsocks服务器](http://tommy88.top/2018/01/27/create-shadowsocks-server-on-windows/)

8. [Shadowsocks服务器搭建及优化解决方案，教你如何正确上网！](http://blog.51cto.com/xvjunjie/2071369)
