     装好OpenClaw下一步！接入飞书限时领API无限调用 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

装好OpenClaw下一步！接入飞书限时领API无限调用
============================

原创 阿竹 AI飞升录 2026-03-04 21:20 浙江

> 原文地址: [https://mp.weixin.qq.com/s/hgaw91zQMzCYFt3cmRxgHA](https://mp.weixin.qq.com/s/hgaw91zQMzCYFt3cmRxgHA)

![image-20260304202053754](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zn0pwgZGuT5FfcIbaszUiaKx6aWXEcFiak2lDTJZUz01c3iaIUIpvJepgmPTI6hApAC7GzNLNMcFHhj9cljUFG8EQqIVqSjCpltwc/640?wx_fmt=png&from=appmsg)上篇把小龙虾装上了，打开浏览器可以对话。但真正好用的是把它接入通道，比如飞书。在群里@它，能查数据、转文档、写日报，不用切窗口，也不用喊同事。
============================================================================================================================================================================================================================================================================

飞书 API 免费额度有限，聊多了要付费。目前飞书开了个口子，可以免费申请取消限额，3 月 31 日截止。前天填的表，昨天就过了，后台额度直接显示不限。

下面先讲怎么领这个权益，再讲如何接入飞书。照着做，30 分钟内能跑通。如果没有安装OpenClaw的朋友，可以先看这篇[十分钟速通！万字OpenClaw新手保姆级部署教程](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484651&idx=1&sn=637ce27d0087e61781fb6294a152c3ab&scene=21#wechat_redirect)

* * *

零、先把飞书 API 无上限权益领了
------------------

领无上限权益这一步，建议在接飞书之前做。领完再接入，后面随便聊。

申请链接：https://bytedance.larkoffice.com/share/base/form/shrcniy7Xzpp1dL75aOPtvEJTZd?from=navigation

![](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zkTeZ1sOVSTMCqEunfWiazy8ianbAGZdLX3dFGh7icm2ncia7lFfMCxjJtZWg7JMdc4wCvDyqyXUSZbOXyh2utnSczX7hGh1kC6LMA/640?wx_fmt=png&from=appmsg)

填完提交，等 1～2 个工作日。通过后进飞书管理后台，额度会变成不限：

![](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zknzKNBVgiauLbT5yKicXpkmybPlRPMq5meCrqETV0dgJojk0iavCbrlaAbAibCSibiasxgrNhqGaUbDzv7MzIdJ4sTWjCj9ibo1eiaUvQ/640?wx_fmt=png&from=appmsg)

申请二维码（备用）：

![](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9znJWty8LnGZEUF5icROpsZziccBVxeo2sJnpVBeECicM6V17A7UMbRYWXRyfyaBgHpsiavf11gbXxnanUBfOUqwUibdwzU51WXiciat0k/640?wx_fmt=png&from=appmsg)

领完这个，再往下接飞书。

* * *

一、接飞书前：先确认两件事
-------------

### 1\. 小龙虾已经跑起来了

执行 openclaw gateway 能正常启动，浏览器访问 http://127.0.0.1:18789 能对话，API Key 已配好（KIMI、MiniMax、GLM 任一家）。如果还没到这一步，先回去把上篇部署教程跑完。

### 2\. 你有飞书企业管理员权限

接飞书需要在飞书开放平台创建应用，需要企业管理员权限。个人版飞书也可以，但必须是管理员。不确定的话，用飞书账号登录 https://open.feishu.cn 试试，能进就能继续。

* * *

二、整体流程：5 步走
-----------

步骤

在哪做

做什么

1

飞书开放平台

创建应用、拿 App ID 和 App Secret

2

飞书开放平台

配置权限、启用机器人、先发布应用

3

你电脑终端

openclaw channels add 配置飞书渠道

4

你电脑终端

openclaw gateway 启动网关

5

飞书开放平台

开启事件订阅长连接、飞书里私聊配对、群里@测试

顺序别乱，尤其是先发布应用再开长连接，否则会一直失败。

* * *

三、飞书侧：创建应用并拿凭证
--------------

### 第一步：打开飞书开放平台

打开 https://open.feishu.cn/app，登录后点创建企业自建应用。

### 第二步：创建企业自建应用

名称填 AI助手 或 小龙虾，描述写内部用的 AI 助手，图标可传可不传。

![](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmfhAIl6ZRcrTAcHGo5DmE9y9qZsdLxQZaqFdHDykiah3vfgBia698iaDiabmjdVGyZhoFLfw6ia8xCfjLUeBwOy6rUIlmeWdBwBaeY/640?wx_fmt=png&from=appmsg)

### 第三步：获取 App ID 和 App Secret

建好后进应用详情，左侧点凭证与基础信息，把 App ID 和 App Secret 记下来。Secret 点查看才显示，只显示一次，务必复制保存，别截图外传。

![](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlibXQlpoMVBnP9B3zQGQonz3CyFVuP6WSvXEJKD5gRQu2Xriay54DerxAmzdq3ia9jAgibVgRVKRtGyVQtpepibyzh29iciayGBicJ2k0/640?wx_fmt=png&from=appmsg)

### 第四步：配置权限

权限这块最容易出错。左侧点权限管理，批量导入权限，在列表里搜机器人相关权限，把收发消息、以应用身份发消息、收私聊、收群消息、收@消息这些都勾上。也可以直接搜 im:message、im:message:send\_as\_bot、im:message:readonly 之类，机器人能用的都勾。点确定保存。

![](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zm5Cs7TVmWhF8ahr86D2xo5zZKvtsGA72XHiaDGEpFLOvATnhoX42sPibhRjDkmHx12r2b6mzwzP6vX4AHVhkDZ13KofU2eAfcWY/640?wx_fmt=png&from=appmsg)

### 第五步：启用机器人能力

点应用能力，找到机器人卡片，启用，设个名字（建议和应用名一致），保存。

![](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zkh0LK1tepaW7MCOr0BHpPBawWLGpyMQcFXNFHFMUvKs0u5qUqCnrp2wSia3Shdm9x4WARicn3DnCfiaqI6oAFRHFvFHS25bwFbLo/640?wx_fmt=png&from=appmsg)

### 第六步：首次发布应用

左侧版本管理与发布，创建版本，版本号填 1.0.0，更新说明写初始版本，保存后申请发布。自己的企业一般自动过。没发布就开长连接，实测会一直失败。

* * *

四、OpenClaw 侧：配置飞书渠道
-------------------

### 第一步：确认飞书插件已启用

回到你电脑，终端执行 `openclaw plugins list`。如果 feishu 是 disabled，执行 `openclaw plugins enable feishu`；如果没有 feishu，执行 `openclaw plugins install @openclaw/feishu`。

### 第二步：添加飞书渠道

再执行 `openclaw channels add`，选 Feishu/Lark，粘贴 App ID 和 App Secret，飞书域名选 feishu.cn，群聊先选 disabled，需要@才回复选 yes。执行 `openclaw channels list` 确认 feishu 是 enabled。

* * *

五、启动网关并开启长连接
------------

### 第一步：启动 Gateway

终端执行 `openclaw gateway`，窗口别关。看到 Gateway listening 就对了。

### 第二步：在飞书平台开启事件订阅

回飞书开放平台，进你的应用，左侧事件与回调，事件订阅方式选长连接，保存。在订阅事件里点添加事件，搜 im.message.receive\_v1，勾选确认。

![](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zlCKTvGvbMmjCGfiacicqVEga1go8OResjkvJYOxaRFc6LaFh9aOQjPQjJfF3cgiaibZb14PNsbpM9MFtzkl4qtzH7tzoFwdNWCKjk/640?wx_fmt=png&from=appmsg)

* * *

六、配对与验证：飞书里和机器人说话
-----------------

### 第一步：私聊触发配对

飞书里搜你的机器人名字，进私聊，发一句你好。机器人会回一条配对提示，里面有一串配对码。复制下来，终端执行：

`openclaw pairing approve feishu 你的配对码   `

比如配对码是 A1B2C3D4，就执行 `openclaw pairing approve feishu A1B2C3D4`。

### 第二步：验证私聊

再回飞书发消息，机器人能正常回就对了。

### 第三步：开启群聊（可选）

私聊通了再开群聊。改 `~/.openclaw/openclaw.json` 里群聊策略为 enabled，或者重新跑一遍 `openclaw channels add` 这次选 enabled。飞书里建个群，添加机器人，群里@它发消息测试。

![d80abaac4553303008442649cd586bad](https://mmbiz.qpic.cn/sz_mmbiz_jpg/JYWVQlsu9zlPmKKhe1yoPt7LXicVZn1pAGhviaicU1BgbwvHCvTceQkCKnwQEhD3nVtQdicmbVdPAgl8nUDibdMlMy55ncIBxkYzbuBEMghIHhvQ/640?wx_fmt=jpeg&from=appmsg)

接好之后，可以让它帮你整理日报、查数据、转文档，比如在群里发一句帮我整理今天的日报，从项目群提取进展等等。

* * *

七、常见问题速查
--------

长连接订阅失败，多半是应用没发布或 Gateway 没启动，先发布、先跑 gateway 再开长连接；发消息没反应，可能是用户没配对，执行 `openclaw pairing list feishu` 看待批准列表，再 approve；群里@没反应，检查群聊开了没、机器人加进群没；机器人乱回，确认配置里需要@才回复是 yes。

* * *

八、安全建议
------

私聊默认 pairing 就行，别改成 all；群聊务必开需要@才回复；App Secret 别外传。

* * *

九、写在最后：几点感受
-----------

接完飞书，小龙虾就真正住进你的工作流了。用了一段时间，有几点感受想分享：

第一，上手和学习的能力飞快。自己能力的边界被大大拓宽了，这种信心非常重要。照着步骤来，小白也能搞定。

第二，创始人一定要下场，一定要在一线。只有自己亲手接、亲手用，才知道哪里会卡、哪里要写清楚。纸上谈兵和真实踩坑，完全是两回事。

第三，不焦虑，要落地。不管外面有多少新模型、新工具，我的团队每天都在用 n8n 工作流、用小龙虾处理业务。变化再多，真正用起来的才有价值。

第四，一个人的公司，一定会大爆发。有很多人利用 AI 开发出自己的系统，而他们很多连代码都不懂。

第五，这一年，人和人的差距，公司和公司的差距，在 AI 下，会学习的和不会学习的，会运用的和不会运用的，会有 10x、100x 的差距。

* * *

如果你按这篇教程接好了飞书，欢迎在评论区晒一晒你的使用场景。有问题也可以留言，大家一起踩坑一起进步。

完整文章源文件打包到公众号里了，有需要的小伙伴公众号后台回复小龙虾自取即可。觉得有用，点个赞和在看。

[十分钟速通！万字OpenClaw新手保姆级部署教程](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484651&idx=1&sn=637ce27d0087e61781fb6294a152c3ab&scene=21#wechat_redirect)

  

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言