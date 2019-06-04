# v2ray
最好用的 V2Ray 一键安装脚本 &amp; 管理脚本

### 安装或卸载
使用 root 用户输入下面命令安装或卸载
```
bash <(curl -s -L https://git.io/v2ray.sh)
```

### 功能特点
- 支持 V2Ray 多数传输协议
- 支持 WebSocket + TLS / HTTP/2
- 支持 动态端口 (WebSocket + TLS，Socks5， HTTP/2 除外)
- 支持 屏蔽广告
- 支持 配置 Shadowsocks
- 支持 下载客户端配置文件 (不用 Xshell 也可以下载)
- 客户端配置文件同时支持 SOCKS 和 HTTP
- 支持 生成 V2Ray 配置二维码链接 (仅适用部分客户端)
- 支持 生成 V2Ray 配置信息链接
- 支持 生成 Shadowsocks 配置二维码链接
- 支持修改 V2Ray 传输协议
- 支持修改 V2Ray 端口
- 支持修改 动态端口
- 支持修改 用户ID
- 支持修改 TLS 域名
- 支持修改 Shadowsocks 端口
- 支持修改 Shadowsocks 密码
- 支持修改 Shadowsocks 加密协议
- 自动启用 BBR 优化 (如果内核支持)
- 集成可选安装 BBR (by teddysun.com)
- 集成可选安装 锐速 (by moeclub.org)
- 一键 查看运行状态 / 查看配置信息 / 启动 / 停止 / 重启 / 更新 / 卸载 / 等等…
- 人性化向导 & 纯净安装 & 卸载彻底

哈哈哈..我故意要写够 23 条的。说着当然，脚本肯定都会有如上所说的功能。

### 快速管理
```
v2ray info 查看 V2Ray 配置信息
v2ray config 修改 V2Ray 配置
v2ray link 生成 V2Ray 配置文件链接
v2ray infolink 生成 V2Ray 配置信息链接
v2ray qr 生成 V2Ray 配置二维码链接
v2ray ss 修改 Shadowsocks 配置
v2ray ssinfo 查看 Shadowsocks 配置信息
v2ray ssqr 生成 Shadowsocks 配置二维码链接
v2ray status 查看 V2Ray 运行状态
v2ray start 启动 V2Ray
v2ray stop 停止 V2Ray
v2ray restart 重启 V2Ray
v2ray log 查看 V2Ray 运行日志
v2ray update 更新 V2Ray
v2ray update.sh 更新 V2Ray 管理脚本
v2ray uninstall 卸载 V2Ray
```

### 配置文件路径
```
V2Ray 配置文件路径：/etc/v2ray/config.json
Caddy 配置文件路径：/etc/caddy/Caddyfile
脚本配置文件路径: /etc/v2ray/233blog_v2ray_backup.conf
```

**警告，请不要修改脚本配置文件，免得出错。。**
如果你不是有特别的需求，也不要修改 V2Ray 配置文件
不过也没事，若你实在想要瞎折腾，出错了的话，你就卸载，然后重装，再出错 ，再卸载，再重装，重复到自己不再想折腾为止。。

### WS+TLS / HTTP2
如果你使用了这两个协议，那么就会使用了脚本自带的 Caddy 集成
不管如何，不建议直接去更改 Caddy 的配置：/etc/caddy/Caddyfile
如果你需要配置其他网站相关，请将网站的配置文件放到 /etc/caddy/sites 目录下，然后重启 Caddy 进程即可，脚本默认生成的 Caddy 的配置会加载 /etc/caddy/sites 这个目录下的所有配置文件。
所以，请将你的网站配置文件放到 /etc/caddy/sites 目录下，完完全全不需要去更改 /etc/caddy/Caddyfile
记得重启 Caddy 进程：service caddy restart

### Caddy 插件相关
本脚本集成了 Caddy，但不集成任何 Caddy 插件，如果你需要安装某些 Caddy 插件，你可以使用官方的 Caddy 安装脚本来一键安装。
本人的脚本集成的 Caddy 的安装路径，跟 Caddy 官方的安装脚本是一致的。所以可以直接安装，不会有任何问题

举个例子，安装包含 http.filebrowser 插件的 Caddy，执行如下命令即可

```
curl https://getcaddy.com | bash -s personal http.filebrowser
```

你可以在 https://caddyserver.com/download 找到 Caddy 更多插件和安装命令。

### 备注
V2Ray 客户端配置文件 SOCKS 监听端口为 2333， HTTP 监听端口为 6666
可能某些 V2Ray 客户端的选项或描述略有不同，但事实上，此脚本显示的 V2Ray 配置信息已经足够详细，由于客户端的不同，请对号入座。
