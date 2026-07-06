     Brief：如何用AI设计出无法复制的产品 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

Brief：如何用AI设计出无法复制的产品
=====================

原创 阿竹 AI飞升录 2026-05-30 10:44 浙江

> 原文地址: [https://mp.weixin.qq.com/s/v1ja5gt1oA5TN6jvdKNb6Q](https://mp.weixin.qq.com/s/v1ja5gt1oA5TN6jvdKNb6Q)

X上有个博主，周末两天做了一个精简版Notion。  
没有团队协作，没有通知流，没有评论。就五个东西：任务、日记、习惯、书签、笔记。一个页面，数据存在本地。

两个人干的活：一个AI出设计，Cursor和Codex写代码。

他把踩完坑之后的完整流程公开了，包括每一步用的提示词和架构设计。

三条原则
----

**先设计流程，再设计像素。**  像素是最后决定的东西。像素之前是屏幕，屏幕之前是状态，状态之前是动作，动作之前是用户到达时想干什么。

**提示词就是简报。**  一行提示词等于一行简报。你不会接受人类设计师的一行简报，也别接受AI的。写500字，告诉它受众、限制、感觉、你欣赏的参考、你拒绝像的东西。

**设计系统放在代码仓库里。**  不在Figma里，不在Notion里。在markdown文件里，跟代码一起提交。放别的地方一定会漂移。

写简报
---

打开笔记本，回答五个问题，想清楚再碰工具。

给谁用的？别写"知识工作者"。写一个具体的人，具体到某个周二早上他打开电脑想干什么。

核心只做一件事。哪件事？

用三个词形容感觉。冷静、锋利、温暖。要具体。

长得像谁？列两三个你愿意被拿来比较的产品。

拒绝像谁？列两三个你宁可删项目也不想被人误认的东西。

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zkz3aluEsSkU1TUAyPr0HiaX6IEqk00F7ib9qJdZLvISaaDChzyHDgcsgZWVAKsKBTOfgkbudvpRmT0hWr1VHR0pSoxmkyxdGup0/640?wx_fmt=png&from=appmsg)

他举了个例子："我试过的每个任务管理App都把我的任务列表当项目计划。我不负责项目，我负责早晨。我想看到四件事，完成三件，关掉页面。"

这里面的人、问题、答案形状都是具体的。没有"AI驱动"，没有"为团队设计"。

这步他花了二十分钟，大部分时间在划掉。

找设计语言
-----

新手写提示词喜欢说"我要简约风"。这跟设计师说"好看点"一样，等于没说。

他的做法：找十几个风格相近的网站，把链接扔给AI，让它自己提炼共性。

关键点：别喂Notion、Linear这种被所有模型嚼烂了的产品。它们的分析你不用AI都能背出来——"Notion-like"、"Linear简洁"、"Stripe优雅"——全是模型见过百万次的废话。去找小众的个人站、开发者做的小工具。模型没分析过，才会真的看像素。

他扔了十三个链接进去。AI回来一段话：深灰色调带纹理质感、等宽字体标注元数据、模块化卡片布局、极简窗口框架、柔和阴影、毛玻璃细节。

最后一句成了整条产品线的锚点： **"精心打磨的安静界面，不是一个吵闹的SaaS仪表盘。"**

后面每一个设计决策都过这句话。某个组件放上去感觉吵了、像SaaS了，砍掉。

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zkHh8MYFmU6Fbnh6lTjIwgccS5ytMeUQoHCwCkjotnEHiaKpD2CPH2bXe3ow0Xe7icYJpib3NNTVajbgjmDEoibsWHe9YnrMtFECY8/640?wx_fmt=png&from=appmsg)

他用的提示词模板：

> 我要给你一组网站链接/截图/录屏，都是我想学习的应用和个人站。你的任务是找到它们的共同点。逆向工程出共享的设计语言，这样我才能用这套语言写简报。
> 
> 输入：\[粘贴链接或上传截图\]
> 
> 输出一个叫 design-library.md 的文件：
> 
>   
> 
> 1.
> 
> 一段话总印象。这套语言在表达什么情绪？给谁用的？它重视什么、回避什么？
> 
> 2.
> 
> 色彩系统。提取所有看到的颜色，每个写明hex值、用在哪、给人什么感觉。
> 
> 3.
> 
> 字体。字体族、粗细、大小层级。
> 
> 4.
> 
> 布局。卡片？列表？留白密度？网格？
> 
> 5.
> 
> 组件特征。圆角大小、阴影风格、边框、动效节奏。
> 
> 6.
> 
> 排除项。这套语言不包含什么？反面是什么？
> 
>   

存为 design-library.md，提交。这个文件可以在多个项目里复用。

画流程
---

大多数人拿到工具就开始画页面。这是错的。

流程不是屏幕。流程是一条路：用户从哪进来、做什么、状态怎么变、到哪结束。先把每条流程用大白话写清楚，再动手画界面。

他用的提示词：

> 我有 design-library.md 和简报作为上下文。请设计这个产品的用户流程。
> 
> 输出 flow.md：
> 
>   
> 
> 1.
> 
> 用户角色。几个角色？各要什么？
> 
> 2.
> 
> 流程清单。每条流程：名称、触发条件、经过的屏幕、状态变化、结束条件。
> 
> 3.
> 
> 屏幕清单。每个屏幕：名称、用途、包含的元素、关联的流程。
> 
> 4.
> 
> 状态转换。从哪个屏幕、到哪个屏幕、由什么操作触发。
> 
> 5.
> 
> 开放问题。简报里任何模糊的地方，列出来。不许猜，逼我回答。
> 
>   
> 
> 约束：
> 
>   
> 
> •
> 
> 不做视觉决策。不要颜色、布局、字体。只管行为。
> 
> •
> 
> 范围要狠。一条流程超过五步，就是两条流程或者产品本身有问题。
> 
> •
> 
> 开放问题是必选项。如果你说没有，说明你没认真看。
> 
>   

AI第一轮给他三个核心流程、六个界面、二十一个状态、八个状态转换。还附了四个开放问题——都是他写得模糊的地方，模型不留情面地指出来了。

第一稿还编了一个"团队共享"流程，简报里根本没提。他删掉，重跑一遍，开放问题归零。

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zkes9Uv9Cc8vZjWiascpjicrLxQXwRqG7ot2DldgsAHZUpflRMw0Hpz58wrDZgUwMegKOJ2LL61CY5qpVKbWDQDGdxc7Oemdgomw/640?wx_fmt=png&from=appmsg)

开放问题是整轮输出里含金量最高的部分。回答完，重跑一遍，直到归零。

你不知道哪些流程经过一个界面，就别画那个界面。仪表盘存在是因为三条流程在那汇合。命令面板存在是因为两条流程可以跳过屏幕加速。流程对了，界面基本是推导出来的。

存为 flow.md，提交。

砍功能
---

PRD是合同。列清楚每一个功能、每一种数据类型、每一个状态变体、每一条验收标准。

他用的提示词：

> 基于简报、design-library.md 和 flow.md，生成产品需求文档 spec.md。
> 
> 包含：
> 
>   
> 
> 1.
> 
> 功能清单。每个功能：名称、描述、关联的流程、验收标准。
> 
> 2.
> 
> 数据类型。每个字段的类型、默认值、约束。
> 
> 3.
> 
> 用户流程。从flow.md精化，补充异常分支。
> 
> 4.
> 
> 状态变体。每种状态的UI表现。
> 
> 5.
> 
> 不做什么（Out of Scope）。必填。写三个这个产品明确不做、也不应该做的事，给出理由。
> 
>   

"不做什么"这节杠杆最大。AI永远想给你加东西——日历集成？加上。番茄钟？加上。天气插件？加上。你不说不，它就一直加。

他的PRD拒绝了三样东西：日历、团队协作、应用内AI助手。三个都没加。

存为 spec.md，提交。

三个方向
----

大多数人的做法：让AI出一个方案，然后在上面改来改去，最后得到一个打磨过的"AI第一直觉"。

他的做法：让它出三个完整方向，互不收敛。

第一个：深色三栏编辑器，Linear风格的严肃工具感。

第二个：每日仪表盘，打开就看到今天要做的事。

第三个：浅色写作界面，宽边距、大字号，为写字而生。

他没选一个。从每个里面挑了喜欢的部分，混在一起。深色主题来自第一个，Today视图来自第二个，编辑器的呼吸感来自第三个。

这四个画面——Today视图 × 编辑器 × 浅色 × 深色——成了整个项目后续所有设计决策的参照系。

第一轮大约60%留下来了，40%砍掉或重写。但有东西摆在那里让你反应，比从白纸开始快了一个数量级。

大部分人跳过这步。他们只出一个方向，然后在上面无限迭代。

状态锁定后，让他输出 style.md：色板、字体层级、布局网格、每个组件及其状态、语气风格。设计到这里定稿。

后端架构
----

AI生成的应用大多死在这一步。前端漂亮，后端一塌糊涂，数据层和UI层搅在一起，最后推倒重来。

他的做法：后端独立设计。

架构图长这样：

    App.tsx (单一状态源)  ├── <Titlebar>  ├── <Sidebar>  ├── <MainContent>  │     ├── <TodayView>  │     │     ├── Focus Card  │     │     ├── Note Card  │     │     ├── Habits Card  │     │     └── Bookmarks Card  │     ├── <PagesView>  │     └── <JournalView>  └── <CommandPalette>useLocalStorage<T>(key, default)  └── window.localStorage

三条铁律：

所有状态放在 App.tsx 里。不搞Redux，不搞Context，不搞Zustand。属性一层层往下传。一个组件树，一个真相来源。

一个Hook管持久化。useLocalStorage 处理读、写、校验、跨标签页同步。没有第二条路进localStorage。

主题用CSS变量。组件只读变量，不知道主题的存在。

再写下四条不可变规则：

1.

App.tsx 是唯一拥有可变状态的文件

2.

所有持久化字段必须走 useLocalStorage，其他地方不能直接访问 localStorage

3.

主题在组件层面是只读的，组件消费CSS变量，不切换class

4.

命令面板是唯一允许同时知道所有视图的组件

存为 architecture.md，提交。

到这里，六个markdown文件齐了：principles.md、design-library.md、flow.md、spec.md、style.md、architecture.md。接下来交给AI写代码。

一建一审
----

Cursor负责写。它直接读 style.md 和 architecture.md，按规范输出代码。搭建骨架、写状态层、从小组件到大组件逐步构建。每写完一个功能，他review一遍。

Codex负责审。它是第二个AI，没写过这段代码，所以没有"自己写的不舍得改"的偏见。它挑类型错误、可访问性回归、规格里写了但实现漏了的边界情况。

一个AI同时干这两个活，"想上线"的心态会压过"找毛病"。两个AI分开，各管各的，bug率断崖式下降。

Cursor花一小时写完，Codex审出六个问题，Cursor修了五个，剩下一个他手改——是一句文案，他想自己写。

落地页
---

别把落地页当附属品。它有自己的简报、自己的设计语言、自己的PRD。

落地页和应用长得相关但不完全一样。每个字都在抢首屏的位置，排版决策需要更密的迭代。

最有效的提示词模式：给三个选项让AI挑一个，然后为自己的选择辩护。给自由度，但不许它骑墙。

踩坑
--

**输出太泛。**  你的简报太泛了。在"拒绝像谁"那里加更多细节。模糊进，模糊出。

**设计系统自相矛盾。**  常见问题。AI在表格里定义了 Muted 是 #9ca3af，然后在三个组件里用了 #a1a1aa。让它自查："读 style.md，列出所有hex值，标记任何定义了两次但值不同的。"它能抓出来。

**代码跟规格对不上。**  AI推断了规格里没写的东西。更新规格，重跑对应阶段。别直接补代码。规格是真相来源，代码是下游。

**流程超过五步。**  超过五步的流程就是两个流程或者产品本身有问题。拆开或者砍掉。

**感觉不对但说不出为什么。**  用两天。记下来哪里不对，带上时间戳。"周二早上我想标记任务完成，点了整行没反应。烦。"具体的问题能生成具体的修复。

品味不可替代
------

整个流程走下来，AI干了大约80%的体力活。剩下的20%是什么？

强调色#fb5607，AI给了六个，他挑了一个。说不出为什么，感觉对了。

任务行点击任意位置就能勾选完成，规格里没写。第三天用的时候觉得烦，加上了。

文案语气，"早安"而不是"嗨"。AI两种都能写，但选哪个是你的事。

砍功能。AI永远给你更多，说不才是你的工作。

Steve Jobs说过一句被所有人引用但没几个人真懂的话："设计不只是外观和感觉，设计是它怎么运作的。"[TASTE：如何构建他人无法复制的竞争优势](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485584&idx=1&sn=5cba18d9b9df00409f263c8f9617c767&scene=21#wechat_redirect)

这篇讲过，他不是在夸周全。他在定义一个优先级。外观和感觉是功能的下游。功能设计对了，外观感觉基本白送。先设计外观，功能会永远跟你打架。

AI工具用得不好，恰好在诱惑你做错误的事。它在生成外观方面太强了，强到你在想清楚组件是干什么用的之前，就已经拿到了一个漂亮的组件库。

抵抗这个。简报、语言、流程、PRD、设计、架构、代码——这个顺序不是随便排的。先问为什么，再问怎么做。

AI给你一千个合理选项，你得知道哪个对。这个"知道"来自你在某个领域里做过、用过、骂过、换过更好的、慢慢长出来的手感。

工具不会给你捷径。工具只是去掉了其他所有借口。

从"想要一个东西存在"到"这个东西存在"之间的时间差，已经压缩到了你把需求说清楚所需的那段时间。

说得清楚，你就能拥有。说不清楚，给你再好的工具也没用。

⭐如果你希望下次也能接受到此等质量的好文 请务必将我们星标，防止迷路！转给你的亲友一起变强！

[一年暴赚45倍，“白毛女”Serenity凭什么？](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485637&idx=1&sn=45b867b10b688b3f20d1af6927427c3b&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言