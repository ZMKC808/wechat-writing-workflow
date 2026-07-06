     免费！DeepSeek-V4-Pro薅羊毛指南 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

免费！DeepSeek-V4-Pro薅羊毛指南
=======================

原创 阿竹 AI飞升录 2026-05-26 11:08 浙江

> 原文地址: [https://mp.weixin.qq.com/s/4uDcnI2TlS8MWHkkeIY2JA](https://mp.weixin.qq.com/s/4uDcnI2TlS8MWHkkeIY2JA)

> 本文仅供技术交流。任何实际操作产生的风险，自行承担。

DeepSeek这半年生态铺得很快。现在好几个渠道可以免费或极低成本用上DeepSeek模型，从V4 Flash到V4 Pro都有。

整理一下最实用的三条路。

Nous Portal
-----------

DeepSeek V4 Flash 已在 Nous Portal 上免费提供，可在 Hermes Agent 中使用！

Hermes Agent是Nous出的AI Agent平台，之前跑他们自己的Hermes模型，现在接入了DeepSeek V4 Flash。日常问答、代码辅助、轻量级Agent任务都够用，速度快延迟低。

入口：https://nousresearch.com

![image-20260526104715578](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zkQw1ILbLZtwHk0AiayiaT5QfBmicv37FibDJPR1rNWJPibppc66Wfq1BoxgVnLqMTZqkMJjNZ2iaLXm3TuAaqlc3fE6BwMelOu549tw/640?wx_fmt=png&from=appmsg)

Freebuff
--------

Freebuff是Codebuff官方出的免费版Coding Agent，主模型直接上DeepSeek V4 Pro。

广告换额度的模式——你看广告，平台拿广告费补贴API成本。每月500次免费额度。

用户也可以自己选择关闭广告，不过免费额度会减少。

### 安装

    npm install -g freebuff

### 运行

    cd your-projectfreebuff

报错的话先设环境变量再跑：

    $env:NODE_OPTIONS='--use-system-ca'freebuff

![98858d8566e83f0257022ffc2b0d3ee5](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9zkBornEdnT6ZiciaA1hC6ViccoicCnfOUdwaabjfxyNW1HJ2bn8Rlv5XJHLHibsRVnic2c2fKCOSNfFdiaJbjicy0Vk6yqMd1ORpGciabvY/640?wx_fmt=jpeg&from=appmsg)

### 用的模型

•

主Coding Agent：DeepSeek V4 Pro（默认）

•

可替代：Kimi K2.6、MiniMax M2.7、DeepSeek V4 Flash

•

文件查找/Research：Gemini 3.1 Flash Lite

•

深度思考（连ChatGPT订阅后）：GPT-5.4

Freebuff和Codebuff共享积分，依赖包一样，装两个没有额外成本。Codebuff用Claude Opus 4.7，Freebuff用DeepSeek V4 Pro。

推荐链接功能尚未正式上线，官网和界面暂时找不到相关入口，格式参考： `   `

`https://codebuff.com/referrals/<username>`

DeepSeek Reasonix
-----------------

自己调DeepSeek API的话，Reasonix能把账单再降一截。这个 **Reasonix** 专为DeepSeek打造的vibe coding工具试了下就中毒了，应该可以大量节省成本，还有web端体验不错。

GitHub：https://github.com/esengine/deepseek-reasonix

原理是prompt caching。每次调API，很多内容是重复的——系统提示词、历史对话、工具定义。Reasonix把这些缓存住，后续调用只发增量部分，按缓存命中价算，比原价便宜不少。

另外对工具调用（function calling）做了原生优化，调用稳定性比通用SDK好。

搭Agent、高频调API、有大量重复prompt的场景用这个最合适。

![图像](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9zniaT8XyeehBLzSVBngWLAZiaSPVMuAB4th17RT4hLKXw9iamBiaQfl80ic1QibtkTQBjMPSwgD3ajkSg3TpicXPK3TdGEibuzjAaMaozk/640?wx_fmt=jpeg&from=appmsg)

三条路怎么选
------

**纯白嫖** ：Nous Portal的V4 Flash，零成本够日常。

**写代码多** ：Freebuff，V4 Pro能力强，500次/月够编程。

**搭系统调API** ：DeepSeek API + Reasonix，缓存命中后费用打折。

三个可以同时用。日常问答走Nous，写代码走Freebuff，搭Agent走Reasonix优化的API。

注意事项
----

Freebuff的DeepSeek V4 Pro会收集数据用于训练，隐私敏感的场景注意一下。

推荐奖励功能（推荐链接拿额外额度）还没正式上线，后续开放了可以互相薅。

Reasonix是开源项目，适合有开发基础的人。不想折腾的话Freebuff和Nous Portal更省事。

⭐如果你希望下次也能接受到此等质量的好文 请务必将我们星标，防止迷路！转给你的亲友一起变强！

[$0搭服务器，甲骨文4核24G白嫖指南](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485572&idx=1&sn=bf27349bec4f1e1f51dc48bdf1b0b971&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言