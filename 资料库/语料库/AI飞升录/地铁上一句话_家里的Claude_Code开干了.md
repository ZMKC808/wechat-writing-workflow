     地铁上一句话，家里的Claude Code开干了 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

地铁上一句话，家里的Claude Code开干了
========================

原创 阿竹 AI飞升录 2026-06-03 13:17 浙江

> 原文地址: [https://mp.weixin.qq.com/s/-uyNGYsljeFzOmvU86RzYA](https://mp.weixin.qq.com/s/-uyNGYsljeFzOmvU86RzYA)

手机可以远程控制家里的AI Agent了，搭完延迟 **30ms** ，文件不上云，出门在外也不停活。

快的方案 **5分钟** 上手，全的方案 **30分钟** 搭完。

Remote Control
--------------

Claude Code自带Remote Control功能，不需要装额外工具。

电脑上开一个session，生成二维码，手机扫一下，浏览器里实时控制。会话始终在本地跑，手机只是遥控器。

操作：

1.

电脑上打开Claude Code，输入  `/rc`

2.

屏幕弹出二维码

3.

手机扫码，浏览器里看到完整会话界面

4.

打字或语音输入，跟坐在电脑前一样

目前需要Max订阅，Pro快了。手机端不能启动新会话，只能控制已经在跑的。网络断了会自动重连。

好处是零配置，坏处是功能基础——只能聊天，不能管文件、切分支。偶尔在外面看看进度，够了。

注意两个坑：先配好MCP再开Remote Control，从手机端没法新加MCP服务器。用  `/rc`  不要用  `claude rc` ，会话中途启动能保留完整对话上下文。

Tailscale + Paseo
-----------------

想要语音输入、多设备接力、多任务并行，得搭一套完整的远程通道。

SSH + Tmux能用，但手机上敲命令极其痛苦，看代码更是折磨。VS Code Remote写代码体验好，但只解决"写代码"这一个问题，Agent编排、语音控制都做不到。

Tailscale + Paseo的组合不一样。手机当遥控器，家里的机器跑AI。支持语音输入，多任务并行，延迟 **30ms** ，文件不上云。代价是一台国内VPS。

Tailscale是什么
------------

一个基于WireGuard的组网工具。装上之后，你的所有设备加入同一个私有网络，分配100.x.x.x的虚拟IP，互相直接访问，就像在同一个局域网里。

不用暴露端口，不需要公网IP，所有流量端对端加密。个人免费，最多 **100台** 设备。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmybgJia7iaOnGwickcI8nibSOQlsxXiaYGWUPRLXt1SokB187VUa2GP5bhcWDSLIj39t1RXOdkXJnAfWEACPk2333poV7ibDL9ic5Aac/640?wx_fmt=png&from=appmsg)

控制台里每台设备的虚拟IP、在线状态、系统版本一目了然。还能看到各设备上运行的服务（SSH、RDP、HTTP），直接复制连接命令或浏览器打开。

Paseo是什么
--------

一个AI Agent编排平台。GitHub  **7000+**  stars，支持Claude Code、Codex、Copilot、OpenCode、Pi五个Agent。

它在你的工作机上跑一个daemon，然后用手机、iPad、任何设备连上来控制。文件、config、MCP servers全部留在本地，不上云。

支持语音输入，STT本地跑不过云。多个workspace独立分支同时开，互不干扰。还能跨设备接力——早上Mac开任务，出门iPad追加指令，晚上手机确认结果。

为什么得自建中继
--------

传统VPN所有流量经过中央服务器，带宽瓶颈，延迟高。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmjFtwHsOBf9FI4h7VCzHpibvYgYvvcLQa3fXQrjJ9FRXia35xA2SJTNnicfic5ftzyaNQ3jAOZnrs8xhAJylKKD2kvBMGic2Drfnnc/640?wx_fmt=png&from=appmsg)

Tailscale的逻辑不同。优先设备间直连，DERP中继只是保底。

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zlI4u4svE2KrebomtlEGMzVt2Y6XImhGvKFPMEia7qDG9ibPK0SmiceQjypEfsllw5k4YhWpMniceSLWyvVzCrhrkDKBh0exicUeibEw/640?wx_fmt=png&from=appmsg)

连接流程：先走DERP中继确保连通，同时并行打洞找直连路径。打洞成功就升级为直连，中继退出；打洞失败就一直走中继兜底。

大多数家用路由器打洞成功率很高。但手机用4G/5G、企业网络、运营商级NAT，打洞会失败，只能靠中继。

问题出在DERP节点上。官方DERP全在国外，中国大陆没有。一旦走中继，流量绕到香港或东京，延迟 **200ms** 起步，偶尔还被封。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9znOXysYaSuVbJ8xItbtD8PAUNTlt6ibAHChUGcmY40FpKNL3u4MMcqAJNEJic3feaKCiamTLTZqNKZiamiama0yJgGMAJzWaCZujdMs/640?wx_fmt=png&from=appmsg)

上图是真实案例：走DERP(jp)延迟 **250-560ms** ，打洞成功后直连降到 **15ms** 。打洞一直失败的话就只能吃这个延迟。

自建一个DERP放在国内VPS上，延迟掉到 **30ms** ，稳定性也好了很多。

搭建步骤
----

### 第一步：VPS上搭DERP

准备一台国内VPS（阿里云/腾讯云轻量型， **2C2G** 够用）。安全组放行：443(TCP)、3478(UDP)、80(TCP)。

**有备案域名（推荐）：**

域名解析relay.yourdomain.com指向VPS IP，申请SSL证书，编译derper运行。

**没备案域名：**

derper会自动生成自签证书。安全组改成放行自定义端口（比如9810/TCP）。

注意：国内VPS + 未备案域名 + 443端口，运营商可能注入RST切断连接。碰到这种情况用非标准端口。

### 第二步：注册到Tailnet

登录Tailscale控制台，Edit ACLs，加入derpMap自定义配置，把VPS加进去。

保存后tailscale status验证，能看到自建节点就成功了。

### 第三步：装Paseo

工作机装Paseo桌面应用，daemon自动启动。查Tailscale IP，配置Paseo监听Tailscale IP而不是127.0.0.1，否则手机访问不到。

编辑~/.paseo/config.json，把listen改成实际Tailscale IP。不要写0.0.0.0，公共WiFi下所有人都能访问你的daemon。

### 第四步：VPS上搭paseo-relay

paseo-relay是独立项目，给Paseo控制通道做中继。只转发加密字节，自己看不到内容。国内不部署的话走官方relay（Cloudflare Workers），连接不稳定。

VPS放行8411/TCP。Docker一行起：

    docker run -d -p 8411:8411 zenghongtu/paseo-relay

在Paseo App里指定自建relay：Settings → Relay → 填入http://你的VPS公网IP:8411。

### 第五步：手机连接

手机装Tailscale和Paseo，同账号加入Tailnet。Paseo里扫描工作机终端的二维码，或手动填100.x.y.z:6767。

连上就能看到工作机上所有Agent，开始控制。

架构长这样
-----

![图片](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmMWZuz2Snay8LTXRWUcRicXwFyANkRLV9P0KYMMJylE9So83PsvFlB4A22SZJqw52B9JPAfJ9cezuZ11smCT64rOaG1MhuAXcY/640?wx_fmt=png&from=appmsg)

手机通过Tailscale连到工作机，工作机上跑Paseo daemon，daemon控制Claude Code等Agent。两条通路各走各的：Tailscale负责设备组网，paseo-relay负责Paseo控制信号。流量全部WireGuard加密。

避坑
--

\-verify-clients必须加。不加的话知道你IP的人都能用你的带宽，搭配-socket=/var/run/tailscale/tailscaled.sock一起用。

工作机关机等于Agent断线。要7×24可用，把Paseo daemon跑在长期在线的Linux服务器上。

OmitDefaultRegions别轻易改成true。保留官方节点作为最终保底，自建节点挂了还有退路。

Paseo默认只监听本机。必须改成Tailscale IP，手机才能连上来。

先配好MCP再开远程控制。手机端没法新加MCP服务器，得在电脑上先配好。

怎么选
---

只想偶尔看看进度、追加指令：Remote Control，扫码就行， **5分钟** 上手。

经常在外面用手机控制AI，想要语音输入、多任务并行、多设备接力：搭Tailscale + Paseo。

建议先用Remote Control体验一下，觉得不够用再搭Tailscale。

常见问题
----

**Remote Control要什么订阅？**  
目前要Max订阅，Pro快了。Tailscale和Paseo免费。

**手机上能开新会话吗？**  
Remote Control不行，只能控制已经在跑的。Paseo可以。

**安全吗？**  
Tailscale端对端加密，paseo-relay只转密文。但一定要加  `-verify-clients` 。

**延迟多少？**  
自建DERP后 **30ms** 左右。不自建走官方节点， **200ms** 起步。

在地铁上举起手机说一句话，家里的AI就开始跑了。到站下车，打开另一个workspace，另一个AI在跑另一个分支。两个任务并行，互不干扰。

如果你有一台长期开着的Mac或Linux机器，又经常需要离开电脑，这套方案值得试。总成本就是一台轻量VPS的钱，工具本身都免费。

Paseo：paseo.sh  
Tailscale：tailscale.com

⭐如果你希望下次也能接受到此等质量的好文 请务必将我们星标，防止迷路！转给你的亲友一起变强！

[全网首发！Agnes AI多模态无限量Token申领教程](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485698&idx=1&sn=f231ee14fc664097bfbf1e7765dcc8fb&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言