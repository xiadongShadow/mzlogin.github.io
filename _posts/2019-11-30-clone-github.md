---
layout: post
title:  配置代理解决国内使用github下载速度很慢的问题
no-post-nav: true
category: GitHub
tags: [GitHub]
copyright: GitHub
excerpt: 
---


使用代理是真的舒服啊

最近拉github代码发现速度巨慢无比，使用网上说的修改host文件的方法没有改善，依旧是几KB/s。突然想起我还有半年的代理SSR服务器，遂想到使用Shadowsocks来设置github代理。

我使用Shadowsocks代理，代理端口为1081。输入git配置命令，
命令如下：

```git config --global http.proxy socks5://127.0.0.1:1081```

此命令是给git设置全局代理，而我们的目的是只需要github上的代码库走代理，所以最终命令如下：

```git config --global http.https://github.com.proxy socks5://127.0.0.1:1081```

查看代理是否设置成功：

```git config -l```


之后重新拉起代码，发现速度已提升至10M/s。问题解决~~

参考：

- [github使用代理](https://www.1cyril.com/githubshi-yong-dai-li/)
