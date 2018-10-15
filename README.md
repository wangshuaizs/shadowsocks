# shadowsocks_on_DigitalOcean

# How to setup

```bash
\# apt-get update && apt-get install -y python-pip && pip install --upgrade pip && apt-get install -y git
 
\# pip install git+https://github.com/shadowsocks/shadowsocks.git@master
 
\# apt-get install build-essential && wget https://github.com/jedisct1/libsodium/releases/download/1.0.8/libsodium-1.0.8.tar.gz && tar xf libsodium-1.0.8.tar.gz && cd libsodium-1.0.8 && ./configure && make -j2 && make install && ldconfig && touch /etc/shadowsocks.json && echo '{"server":"::", "server_port":8388, "local_address": "127.0.0.1", "local_port":1080, "password":"xxxx", "timeout":300, "method":"chacha20", "fast_open": false }' > /etc/shadowsocks.json && ssserver -c /etc/shadowsocks.json -d start
```

# References
1. [DigitalOcean搭建Shadowsocks](https://blog.csdn.net/bleachswh/article/details/73896348)

2. [升级pip后出现ImportError: cannot import name main](https://blog.csdn.net/accumulate_zhang/article/details/80269313)

3. [查看IP地址](https://whoer.net/zh)

4. [ip111](http://ip111.cn/)

5. [shadowsocks-windows](https://github.com/shadowsocks/shadowsocks-windows/releases)

6. [other shadowsocks client](https://shadowsocks.org/en/download/clients.html)