     Fable 5被大神攻破，美国选择一刀切：非公民全禁 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

Fable 5被大神攻破，美国选择一刀切：非公民全禁
==========================

原创 阿竹 AI飞升录 2026-06-13 11:11 浙江

> 原文地址: [https://mp.weixin.qq.com/s/0qMc2utewEiAsUMQciwLaA](https://mp.weixin.qq.com/s/0qMc2utewEiAsUMQciwLaA)

没想到啊，Anthropic最强的模型Fable 5，上线没多久就被一个安全研究者给突破了。

美国政府的反应更直接： **下架，非美国公民全部禁用。**

具体怎么回事？
-------

6月11日，美国政府给Anthropic下了一道出口管制指令： **立即停止向所有外国公民提供Fable 5和Mythos 5。**

理由是国家安全。

**彻底断供** ，没有中间地带。

而且范围宽得离谱：不管你在美国境内还是境外，只要不是美国公民，统统不能用。连Anthropic内部的外籍员工都被限制了。

问题是Anthropic根本没办法快速、准确地只屏蔽非美国人。为了合规，只能把Fable 5和Mythos 5对所有客户全部关掉。

目前Fable 5还留在模型选择器上，但已经无法调用。新会话默认回退到Opus 4.8。其他模型不受影响。

![上传图片](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zk6ic3qt7IAHXGE1u3vPnTYMqBodzXLsHTdCHHWNvR6Y8ayXYIVcnSgiabgNoI2PKU1q1RLMjFibQmTpzuuD8o8dVlE5k265xh1FI/640?wx_fmt=png&from=appmsg)

导火索：一个叫Pliny的大神
---------------

这事的导火索，是一个叫Pliny的安全研究者。

他在Twitter上公开宣布： **用绕过安全机制的Opus 4.8，把Fable 5的安全防线给突破了。**  还顺手把Fable 5的12万字符系统提示公开到了GitHub。

他用了什么思路？

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9zmOia2UibqgaMmHrricOZMEuiaxv1FfuK9hAicxJFDDg3xjCRbD5icpAMp8EXAE8tPmmXEVq2TRkrZ2gT1zq3UhJiaMvtO6fUNkcIia6eE/640?wx_fmt=jpeg&from=appmsg)

**分解重组** 是最有效的一招。直接要某个受限内容会被拦，但如果拆成多个无害的小块，分别问，模型就容易回答。再用已绕过安全机制的Opus帮忙拼回去。

**Unicode绕过** 也管用。用变体字符、同形异义字替换敏感关键词，过滤器就"看不见"完整意图了。

还有 **长上下文走私** ——用虚构故事、学术研究等框架包装请求，在多轮对话中逐步把意图"走私"过去。

最巧妙的是 **自己人打自己人** ：Fable 5对高风险查询会fallback到较弱的Opus 4.8，Pliny先用已绕过安全机制的Opus生成针对Fable的提示，再反过来突破Fable。

另外还有一招： **意图分类不一致** 。同一件事换个表述方式，模型的判断就不一样了。

Anthropic不服
-----------

Anthropic的反驳有四点：

1.

Fable 5上线前经过了数千小时的红队测试，测试方包括美国本土AI团队、美国政府机构、第三方机构

2.

截至目前，政府只给了口头描述，没给任何书面证据

3.

这种绕过安全机制的能力不是Fable 5独有的，类似手段在GPT-5.5等其他模型上同样存在

4.

这种绕过是非通用型的，只在极窄的范围内有效，不会构成重大威胁

Anthropic的原话： **如果仅因为"存在非通用型绕过安全机制漏洞"就强制下架商业AI模型，那行业内所有新模型的部署都会陷入停滞。**

他们正在跟政府沟通，争取尽快恢复访问。

最讽刺的地方来了
--------

Anthropic一直是AI行业里最积极兜售"AI安全风险"叙事的公司。他们反复主张，应该对高风险模型部署拥有干预能力。

结果最先被按下暂停键的，恰恰是Anthropic自己。

评论区骂声一片。有人说这是"搬起石头砸自己的脚"，有人说"以后谁还敢做安全研究"。

Anthropic自己也承认这些漏洞"很轻微"、"非通用"、"其他模型也有"。但政府不管——只要有绕过安全机制的可能，就得下架。

这事影响有多大？
--------

如果"存在绕过安全机制就下架"成为标准，那所有AI模型都得下架。没有哪个模型是100%安全的。

AI公司想快速迭代，政府想管控风险。两个目标天然冲突。

Anthropic是AI安全的旗手，但他们的模型第一个被安全理由下架了。

Fable 5什么时候恢复？不知道。目前只说"正在沟通"。

⭐如果你希望下次也能接受到此等质量的好文 请务必将我们星标，防止迷路！转给你的朋友一起变强！

[别再卷提示词了！Claude Fable 5发布后，顶级工程师都在搭循环](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485891&idx=1&sn=80150fef7de5d8541ec66f19b2301653&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言