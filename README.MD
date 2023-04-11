https://hub.docker.com/r/teddysun/shadowsocks-libev
$ docker pull teddysun/shadowsocks-libev
$ mkdir -p /etc/shadowsocks-libev
$ cat > /etc/shadowsocks-libev/config.json <<EOF
{
    "server":"0.0.0.0",
    "server_port":9000,
    "password":"password0",
    "timeout":300,
    "method":"aes-256-gcm",
    "fast_open":false,
    "nameserver":"8.8.8.8",
    "mode":"tcp_and_udp"
}
EOF
$ docker run -d -p 9000:9000 -p 9000:9000/udp -e TZ=Asia/Jakarta --name ss-libev --restart=always -v /etc/shadowsocks-libev:/etc/shadowsocks-libev teddysun/shadowsocks-libev



https://hub.docker.com/r/teddysun/shadowsocks-go/
$ docker pull teddysun/shadowsocks-go
$ mkdir -p /etc/shadowsocks-go
$ cat > /etc/shadowsocks-go/config.json <<EOF
{
    "server":"0.0.0.0",
    "server_port":8388,
    "local_port":1080,
    "password":"password0",
    "method":"aes-256-cfb",
    "timeout":120
}
EOF

$ docker run -d -p 8388:8388 -p 8388:8388/udp  -e TZ=Asia/Jakarta --name ss-go --restart=always -v /etc/shadowsocks-go:/etc/shadowsocks-go teddysun/shadowsocks-go


https://hub.docker.com/r/teddysun/shadowsocks-rust/
$ docker pull teddysun/shadowsocks-rust
$ mkdir -p /etc/shadowsocks-rust
$ cat > /etc/shadowsocks-rust/config.json <<EOF
{
    "server":"0.0.0.0",
    "server_port":9090,
    "password":"password0",
    "timeout":300,
    "method":"aes-256-gcm",
    "nameserver":"8.8.8.8",
    "mode":"tcp_and_udp",
    "plugin":"v2ray-plugin",
    "plugin_opts":"server"
}
EOF

$ docker run -d -p 9090:9090 -p 9090:9090/udp -e TZ=Asia/Jakarta --name ss-rust --restart=always -v /etc/shadowsocks-rust:/etc/shadowsocks-rust teddysun/shadowsocks-rust




#### Format Akun
https://blog.vpngame.com/openwrt/kumpulan-daftar-format-akun-untuk-openclash/#Vmess_WS_SNI
