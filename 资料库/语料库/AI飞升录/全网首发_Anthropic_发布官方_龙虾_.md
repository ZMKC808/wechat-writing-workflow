     全网首发，Anthropic 发布官方「龙虾」 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

全网首发，Anthropic 发布官方「龙虾」
=======================

原创 阿竹 AI飞升录 2026-03-24 20:05

> 原文地址: [https://mp.weixin.qq.com/s/7MddRR8mbaENsmnfV4gWFg](https://mp.weixin.qq.com/s/7MddRR8mbaENsmnfV4gWFg)

Anthropic 今天一口气发了三个东西——Computer Use（电脑控制）、/schedule（云端定时任务）、Claude Code Desktop，三个功能同时上线。
=========================================================================================

接管你的电脑
------

先说最炸的那个。

Claude 现在能直接控制你的 Mac 了。鼠标、键盘、屏幕，全都归它管。

Anthropic 产品负责人 Felix Rieseberg 发了条推，配了段 demo 视频，165 万人看了。他的原话是：

\> 今天我们发布了一项功能，让 Claude 可以控制你的电脑——鼠标、键盘和屏幕，赋予它使用任何应用程序的能力。

注意，**任何应用程序。**不只是浏览器，不只是终端，是你电脑上所有能用鼠标键盘操作的东西。

手机发令，电脑干活
---------

视频里展示了三个真实场景，全程通过手机上的 Dispatch 应用远程操控。

### 场景一：导出 PPT 并附到日历

用户在路上赶着去赴约，掏出手机跟 Claude 说：「帮我把 pitch deck 导出成 PDF，附到下午 2 点的会议邀请里。」

![Dispatch 远程操控 Claude 导出 PPT 并附到日历](https://mmbiz.qpic.cn/sz_mmbiz_gif/ZKqVLiaIpzFlW0dLcIA4NoLs0eWjDicDqCfwbyjJvia5DTZb6HmfElSmaqf5xs7lVjC2dEiaEzemzR52iamvibIwFYleETnfFd4ssqHm5OlmCaftY/640?from=appmsg&tp=webp&wxfrom=5&wx_lazy=1)

Claude 在他电脑上打开了 PowerPoint，点菜单导出 PDF，切到日历应用，找到下午 2 点那个会，把 PDF 附进去。

回复是：「搞定了，抓的是你今早 9:47 编辑的版本，全质量导出，可以走了。」

整个过程，人在路上赶路。

### 场景二：启动开发服务器并截图

用户说：「启动服务，截个 Library 页面，3 点 demo 前发给我。」

![Claude 启动开发服务器并截取应用页面](https://mmbiz.qpic.cn/sz_mmbiz_gif/ZKqVLiaIpzFmb6tx9YGT0LlaqBPrct15PWTI6xzr2dXBhzLsmTZypQKNM8YqpVDwbH53rPVOViaxAoEQcLm3gaeBuGCFOEmMEackiayDJMtIKA/640?from=appmsg&tp=webp&wxfrom=5&wx_lazy=1)

Claude 调起 Claude Code，跑 npm 命令起服务，再打开浏览器访问 localhost，找到 Library 页面，截图发回。

这个场景有点意思，它同时用了两套能力：命令行执行加屏幕操控，无缝衔接，没有任何中断。

### 场景三：批量处理 133 张照片

用户让它把桌面上的店铺图片统一处理：调到 1200px PNG，右下角加白色 logo，「我没时间自己弄了」。

![Claude 批量处理 133 张照片并添加水印](https://mmbiz.qpic.cn/mmbiz_gif/ZKqVLiaIpzFlic3FD2zicOfQyX632Nh6ibKaEtE66xB4uF1NJxy9NElpVZM9jGwaIIFPkVibDHOv1aLBiaSX4RKkWo1qbn5FqiaON9lLlXYbDHz3R4/640?from=appmsg&tp=webp&wxfrom=5&wx_lazy=1)

Claude 打开图片编辑器，加载照片，设参数，批量跑完。回复：「搞定了，133 张已经放到新文件夹里。」

133 张，不是写脚本慢慢跑，是直接操控图片编辑器挨个处理。

云端龙虾：/schedule
--------------

然后是 /schedule，这个我觉得更值得单独说。

之前 Claude Code 有个 /loop 命令，能在本地会话里定期执行任务。但那是本地龙虾，养在你自己的终端里，终端一关就没了。

/schedule 是云端龙虾。跑在 Anthropic 的服务器上，你合上电脑去喝咖啡，这只龙虾照样在干活，到点就动。一句话就能创建任务：

`    /schedule 每天早上检查昨天合并的所有 PR，      根据变更更新文档，      然后通过 Slack 发到 #docs-update 频道       `

Claude 回：「任务创建成功，工作日早上 9 点执行。」

Anthropic 工程师 Noah Zweben 分享了他们内部的一个用法：有一个定时 Claude 任务，全自动维护一个 Go 版的 twin library，对应他们正在开发的 Python 库。Python 那边改了 API，Claude 自动检测到变更，自动把 Go 版本同步跟上。

一个 agent 在默默维护整个代码库，不用人盯。

律师函彩蛋
-----

说到龙虾，得讲个小故事。

那个叫 ClawdBot 的开源项目——就是后来改名叫 OpenClaw 那个——做的就是给 Claude Code 加定时任务、远程控制这些功能。当时不少人建议 Anthropic 直接收购它。

Anthropic 没有，反手发了律师函。

现在回头看，原因不难猜。/schedule、Dispatch、Computer Use，一个接一个往外推，而且比社区项目做得更深、更原生。ClawdBot 当初叫这个名字，是 Claw 加 Claude 的谐音。而 Anthropic 自己做的这套东西，确实更像一只真正的龙虾了。

停不下来
----

我把 2026 年开年到现在 Anthropic 的更新列了一下：

\- **1 月：**Claude Cowork 上线

\- **2 月：**Opus 4.6、Sonnet 4.6 发布；PowerPoint、Excel 集成；Cowork 插件；Remote Control

\- **3 月：**Memory 免费开放；Marketplace 上线；Code Review；图表功能；百万上下文；Channels

\- **3 月 24 日：**Computer Use + /schedule + Claude Code Desktop

Felix 自己回复了一位问 Windows 支持的用户：「我们会让你用上的，这是列表上的下一项。」

你们到底睡不睡觉。

该选谁？
----

Claude Computer Use 目前只支持 macOS，要 Pro 或 Max 订阅，对中国用户来说账号本来就不好注册，还经常封号。

**选 Claude 的情况：** 能搞定订阅、喜欢现成产品不想折腾。零配置，一键开，四层安全防护是官方兜底的，开源工具很难复制。

**选 OpenClaw 的情况：** 技术极客、隐私敏感、想深度定制。数据本地、全平台支持、开源可改。

这不是一道非此即彼的题，取决于你在哪个位置。

有个网友说得挺准的：Dispatch 加 Computer Use 这个组合，模型在云端思考，在你的硬件上执行，手机发任务，电脑干活，结果推回来。没有数据外泄，也不需要沙箱。

他说这个组合大部分人还没反应过来。我觉得他说的对。

* * *

⭐以上，既然看到这里了，如果觉得不错，随手点个赞、在看、转发三连吧，谢谢你看我的文章，我们下次再见~

[刚刚，微信可以接入"龙虾"了，10分钟教你搞定](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484937&idx=1&sn=e267b0c8b885ae5fa8094002d5d56464&scene=21#wechat_redirect)

[实测MiniMax M2.7：当所有人还在折腾小龙虾，它开始自己迭代自己了](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484925&idx=1&sn=6a213f3ec29f7688c215f2001ab95f96&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言