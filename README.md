# frank.github.io
mark
lubuntu使用shadowsocks翻墙

 先说说最近折腾的经验，以免后来者浪费时间。最近几天无聊，想试一下 Manjaro 18，没想到他要求 uefi+gpt，我的老电脑没这些，只能放弃。然后选了 lubuntu。ubuntu 我用过，他在使用 shadowsocks 时，有图形界面来配置代理，网上有很多文章。但是 lubuntu 没有，包括在 ubuntu 上启动 lxde 桌面也一样。网上的这个方案是没法用的：

http_proxy=http://myproxy.server.com:8080/
https_proxy=http://myproxy.server.com:8080/
ftp_proxy=http://myproxy.server.com:8080/
    因为 shadowsocks 在本地也使用的是 socks5 协议，以上方案是把 http 流量装换成另一个方向的 http 流量，是不行的。 shadowsocks 有个选项http(s)，但是试一下不行，不知道为什么。甚至把以上内容写入 /etc/environment 以后 shadowsocks 直接连不上服务器。我猜是因为 shadowsocks 的流量也要按照 /etc/environment 的配置走，虽然里边没有 socks5_proxy 。我就不追究了。

    现在就需要把 http 的流量转换为 socks5 。我用的 proxychains （参见Linux 下使用 SSR + ProxyChains 代理终端流量），也可以用 privoxy （参见Ubuntu 终端使用shadowsocks全局代理）。chrome 浏览器需要插件 SwitchyOmega （Chrome + Proxy SwitchyOmega 设置）。用 crx 安装的插件，文件夹不能移动到别处，移走了浏览器的插件也没了，好神奇。如果有别的软件还需要专门转换。

    Chrome 浏览器上谷歌可以用“谷歌访问助手”，国内的插件下载商店就可以下载。

    另外，在大家熟知的浏览器搜索 shadowsocks，是搜不出什么的。推荐两个搜索：https://dogedoge.com      https://seeres.com/
