lubuntu使用SSR 酸酸乳（2019年）

    不知道为什么以下方法对lubuntu没用：
    # export http_proxy=http://129.156.243.243:3128
    # export https_proxy=http://129.156.243.243:3128    
    我猜以上方案是把 http 流量转换成 http 流量，所以不行。

    现在就需要把 http 的流量转换为 shadowsocks5 。我用的 proxychains （参见Linux 下使用 SSR + ProxyChains 代理终端流量https://abelsu7.top/2019/02/24/ssr-proxychains4-on-linux/），
    也可以用 privoxy （参见Ubuntu 终端使用sss全局代里https://www.ichenfei.com/ubuntu%E7%BB%88%E7%AB%AF%E4%BD%BF%E7%94%A8shadowssocks%E5%85%A8%E5%B1%80%E4%BB%A3%E7%90%86.html）。
    chrome 浏览器需要插件 SwitchyOmega （Chrome + Proxy SwitchyOmega 设置https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/7-2-chrome-setup-guide-cn.md）。用 crx 安装的插件，文件夹不能移动到别处，移走了浏览器的插件也没了，好神奇。

    注意：proxychains 只是把终端流量引向 shadowsocks 代理，别的软件流量依然不会通过 shadowsocks 代理，使用别的软件还需要专门用什么工具去转换。下面介绍几个从网上搜集的但是我没有实际测试的全局代理的方法：

    1、前文讲的 privoxy 可以将 shadowsocks 转换为全局的 http 代理。

    2、3proxy 介绍https://www.cnblogs.com/hjbf/p/10154353.html

    3、privoxy 和 polipo 使用 教程https://juejin.im/post/5c91ff5ee51d4534446edb9a

    Android Studio 的proxy设置参见这里https://www.jianshu.com/p/fad93920dac4

    Chrome 浏览器上谷歌可以用“谷歌访问助手”，国内的插件下载商店就可以下载。

    另外，在大家熟知的浏览器搜索 shadowsocks，是搜不出什么的。推荐两个搜索：https://dogedoge.com      https://seeres.com/

    再分享一个代理 快代理 https://www.kuaidaili.com/free/。免费 ss 帐号 ： freess.site
