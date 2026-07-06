     技术纯小白如何用AI开发全网首个小报童导出插件？（保姆级教程） \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

技术纯小白如何用AI开发全网首个小报童导出插件？（保姆级教程）
===============================

原创 阿竹 AI飞升录 2025-07-31 10:43 浙江

> 原文地址: [https://mp.weixin.qq.com/s/9VQmOqxtpIOlsz65Xg1TeA](https://mp.weixin.qq.com/s/9VQmOqxtpIOlsz65Xg1TeA)

![](https://mmbiz.qpic.cn/mmbiz_png/FTOSnyk3X7P61P7RXpdjJL9BVEOqEd0wCb7QhItNauEH6oSxCG2FyTUEjic2sbiaONas4NkyPUcxYuYPvEs3YruQ/640?wx_fmt=png&from=appmsg)

作为小报童的付费用户，我一直有个困扰：花钱买的内容，却没法自由使用。想复制一段话做笔记，得一个字一个字敲；想导出买过的内容，根本不可能；更要命的是，一旦作者删除内容或者平台出问题，这些付费的内容就白买了。说白了，我买的只是"临时阅读权"。

虽然是个编程小白，连最基本的HTML标签都搞不清，但这种体验实在让人抓狂。既然平台没有这些功能，那就想办法"曲线救国"。

尝试用Manus解决
----------

一开始我完全不知道怎么下手。谷歌搜索"小报童文章导出"之类的工具，要么是单篇复制的油猴脚本，但动辄几十上百篇文章，想想都觉得手指要废。要么只有一篇复杂的n8n教程`https://www.aigc1.com/article/n8n-crawl4ai-xiaobot` 

于是我想用Manus试试能否基于这篇n8n的教程做出一个谷歌小报童导出插件，于是我把需求告诉它

我给Manus的提示词是：

`https://www.aigc1.com/article/n8n-crawl4ai-xiaobot 文章提及的n8n批量下载小报童文章的方法用谷歌插件可以实现吗，如果可以的话，我需要你参考这篇文章的技术路径，基于第一性原理开发一个可以批量下载小报童文章（md格式）的谷歌插件，可以保存到本地，保存方式分为zip压缩包保存和单篇保存，注意文章中提到的api、签名或者权限等问题。   `

走我的Manu邀请链接 你可以领500积分

`https://manus.im/invitation/NBPXZPXCH9HMOPH`

它帮我梳理了几个关键点：

*   怎么从网页抓取文章内容
    
*   怎么转换成Markdown格式
    
*   怎么保存到本地
    
*   怎么让操作简单易用
    

问题1：插件无法开始运行
------------

当我满心欢喜地试用第一个版本时，很快就遇到报错：`Extension context invalidated`。

![](https://mmbiz.qpic.cn/mmbiz_png/FTOSnyk3X7P61P7RXpdjJL9BVEOqEd0wfMHra5I4NqOMVBKK42gk00iaxarsbVX2udPJ9xsheYKU0icBHEK1icODQ/640?wx_fmt=png&from=appmsg)

![](https://mmbiz.qpic.cn/mmbiz_png/FTOSnyk3X7P61P7RXpdjJL9BVEOqEd0wbEv5FdOglLicWrIz3JhgrqicOiawqogePgOVicm0U4vKdY1ibWHy1z1vFpA/640?wx_fmt=png&from=appmsg)

插件打开后一直处于“正在下载状态”，这是Chrome扩展的"上下文失效"问题，简单说就是插件和网页之间的通信断了。

解决方案：API拦截技术
------------

让manus修正了很多次都没有成功，还是这个报错，最后这个错误点好了。但是更严重的问题是：小报童的文章不是一次性加载的，有时候加载不全，有时候会卡住。就比如40篇文章，我只能抓取20篇。我猜想这个“滚动加载”技术可能是错误的。

于是我又回看"n8n抓取小报童"的文章，虽然用的是不同工具，但原理相同，它提到了一个重要技术——API拦截。

我突然意识到，小报童的文章数据是通过API接口加载的。如果能直接拦截这些API请求，不就能拿到最原始、最完整的数据了吗？

把这个想法告诉它后，立刻开始研究API拦截技术，重写插件的核心代码。新版本不再完全依赖滚动，而是直接拦截小报童的API响应获取数据。

这个方法的优势很明显：

*   数据完整，不会遗漏任何文章
    
*   获取的是结构化数据，处理起来更简单
    
*   性能更好，避免了复杂的页面解析
    

问题2：UI界面消失
----------

API拦截版本做好后，新问题又来了——插件界面不见了。之前右上角的小下载按钮，直接"失踪"了。

又开始排查UI显示问题，增加调试信息，优化UI创建逻辑，甚至用`!important`来确保样式不被覆盖。经过一番折腾，界面终于重新出现。

问题3：文章导出zip失败
-------------

正当以为一切顺利时，我尝试下载ZIP文件，又报错了：`ZIP生成失败: JSZip is not defined`。

![](https://mmbiz.qpic.cn/mmbiz_png/FTOSnyk3X7P61P7RXpdjJL9BVEOqEd0wGsY5IxbALbD2MEoZDgHZFbcFkWnkGvOunaoEOhD5RdFS9UgAV0JNQQ/640?wx_fmt=png&from=appmsg)

我反复查了好几遍，明明没有空标题啊。而且十几篇文章能下载ZIP，一百多篇就不行。

接下来就是我和Manus的"拉锯战"：

*   v3.1.2版本：修复null错误，结果少量文章也提示"ZIP不可用"
    
*   v3.1.3调试版本：为了定位问题搞了超详细日志，结果连文章数据都加载不出来
    
*   v3.1.4版本：修复数据加载问题，又把ZIP生成搞坏了
    
*   v3.1.5版本：采用保守修复策略，结果数据还是加载不出来
    

我当时搞到深夜，真的很崩溃，一度想放弃了。为什么改了这么多版本还是不好用？到底哪里出问题了？

解决方案：确保JSZip在主脚本之前加载
--------------------

我决定彻底回溯到最初能正常获取数据的版本，然后只针对ZIP生成失败进行最小化修复。

但又报错了：`JSZip is not defined`。

这时才发现真正原因：之前为了解决UI问题，把JSZip的加载方式从配置文件里移除了，改成动态加载。回溯版本时，只复制了代码，却忘了把JSZip引用加回来。

这就像做饭时准备食材的顺序搞错了。JSZip是"食材"，处理脚本是"厨师"，厨师不能在食材还没到位时就开始做饭。解决方案很简单，但对我这个小白来说却是醍醐灌顶：确保JSZip在主脚本之前加载。

修改了配置文件，将`jszip.min.js`放在主脚本前面：

`"content_scripts": [     {       "matches": ["https://xiaobot.net/*"],       "js": ["src/jszip.min.js", "src/content_v3_original.js"],       "run_at": "document_end"     }   ]   `

仅仅调整了文件加载顺序，问题就解决了。

完美实现
----

这次我怀着忐忑心情安装新版本。终于：数据获取正常，UI界面正常，ZIP文件成功生成，即使100多篇文章也能顺利打包。

整个插件的操作流程很简单：

1.  打开小报童专栏页面
    
2.  点击浏览器右上角插件图标
    
3.  将页面滚动到底部保证所有文章能够完全加载
    
4.  点击"开始抓取"，等待自动运行
    
5.  选择下载方式（ZIP、单个文件或合并文件），点击下载
    

插件提供了多种下载选项：

*   ZIP打包：所有文章打包成一个文件，方便归档
    
*   单个文件：只下载某几篇文章
    
*   合并文件：把所有文章放在一个文件里连续阅读
    

![](https://mmbiz.qpic.cn/mmbiz_jpg/FTOSnyk3X7P61P7RXpdjJL9BVEOqEd0wuMIVguQxfLiciblaP6OKy320vSibgZnWXiajibw1DjWm1EQpnib11Auqc9rw/640?wx_fmt=jpeg&from=appmsg)

![](https://mmbiz.qpic.cn/mmbiz_jpg/FTOSnyk3X7P61P7RXpdjJL9BVEOqEd0w87S1Zxab6a7E6kicmASJ0pxVq2YcL86aiaJVMe9bgMN2O4a9lsJYlnxQ/640?wx_fmt=jpeg&from=appmsg)

END
---

这里是AI飞升录，持续分享技术纯小白的AI实战教程。

**以上，看完觉得不错，随手点个赞、在看、转发三连吧，如果想第一时间收到推送，也可以给我个星标⭐**

插件源文件我打包到公众号里了，有需要的小伙伴公众号后台回复`小报童`自取即可

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言