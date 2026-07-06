     刚刚！苹果AI应用商店要来了 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

刚刚！苹果AI应用商店要来了
==============

原创 阿竹 AI飞升录 2026-03-31 14:14 浙江

> 原文地址: [https://mp.weixin.qq.com/s/2yOnbNilN9J6kXF6MMaVVA](https://mp.weixin.qq.com/s/2yOnbNilN9J6kXF6MMaVVA)

苹果要做 AI 应用商店了。按目前放出的消息，iOS 27 会上 Siri Extensions，App Store 也会单独开分区，把第三方 AI 工具接进来。

这件事的重点在于，苹果把入口、分发和交易又收回到自己体系里了，带来的变化不只是多了几个 AI 功能。

![WWDC26官网公告截图](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zlgCGt4j7c2VhtIPCfkT1e6twmZgTexvia1NaLSQDE5BREYyKiaPqqZslluv3TMDDqbwvT2ol4pZvUsZx8Sg1Oiav9laBKH8VpTtk/640?from=appmsg)

我不打算把它当成概念新闻。下面我按“怎么接入、谁先受影响、开发者该怎么做”三条线讲清楚，你看完就能判断是不是新机会窗口。

1）核心变化
------

我以前总把苹果 AI 理解成“自己训练模型，然后跟 OpenAI 正面打”。最近这批消息放一起看，更像是另一条路：苹果做操作系统入口和交易市场，模型能力交给第三方补齐。

这条路在商业上很苹果。硬件继续卖，系统继续控，服务继续抽成。你可以把它理解成“AI 版 App Store 逻辑”：我负责把场子搭好、把流量带来，开发者负责把能力做出来。

对普通人来说，这就是体验变化。以前你要先想“我该开哪个 AI App”，以后可能变成“我直接跟 Siri 说，背后由哪个模型处理由系统分发”。

2）为什么是现在
--------

从多家报道的共同口径看，苹果内部也承认，短时间把自研模型追到第一梯队，不现实。它现在走的是“把模型接入能力做成标准接口”这条路。

这个决定很现实。因为模型能力更新太快，今天第一名，明天就可能换人。平台型公司如果把自己绑死在单一模型上，节奏很容易被带着跑。

我自己做内容这段时间最大的体感是：AI 工具的生命周期缩得非常短，接口和入口反而越来越值钱。苹果现在抢的，恰恰是这个“入口层议价权”。

3）Extensions 是什么
----------------

我在看 iOS 27 相关报道时，反复看到一个关键词：Extensions。简单说就是，第三方 AI 能以“扩展”的形式接进 Siri 和系统能力。

这意味着什么？意味着 AI 会从独立 App 往系统能力插件走。你不一定每天点开某个 AI 图标，但你会在写字、搜东西、改邮件、调日程时被动用到它。

这对开发者是个大变化。过去你拼的是拉新下载；以后你拼的是“能不能进入系统默认调用链”。前者是投流问题，后者是产品能力和规则适配问题。

![](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9znWwFLzIluC54IIO1X200GbKdC6iaPxIySUNvJkKLeYs5Oszx7cW4NibCEaGEgH7HFcQXILBLxzhWzqCQkh4Blicp70KOHblKibAGo/640?wx_fmt=png&from=appmsg)

4）Gemini怎么补位
------------

报道里提到，苹果会和谷歌联动，把 Gemini 的能力接进 Siri 的整体体验。我的理解是：它不打算短期把自研模型追到顶尖，所以先用外部强能力把体验补齐。

当你发起更复杂的请求时，系统把这些能力拼起来，结果会更贴近你的意图。你感受到的是“同一个 Siri 做完更多事”。

至于谁会先被影响，我更盯着那类工具：以前靠独立 App 的流程存在感，现在要证明自己接得进系统工作流。路径多一步，在移动端就很容易掉队。

5）开发者真正门槛
---------

我跟做工具的朋友聊过，他一句话很直白：上架只是门票，被系统调用才是票房。这个判断我很认同。

如果未来有 AI Extensions 分区，开发者真正要做的是三件事：把能力模块化、把响应速度做稳、把结果可控性做高。简单说就是，你要像“系统零件”一样可靠，不要只做“单点产品”的炫技。

这对创业团队是好事也是压力。好处是不用从零教一遍，系统会带流量；压力是你必须满足平台级标准，一旦稳定性差，很快就会被替换。

6）会不会再现窗口期
----------

我不敢说会完全重演，但窗口味道已经有了。每次平台切新范式，都会出现一批“看起来不大、但增长很快”的工具形态。

移动互联网早期是拍照、笔记、效率小工具；AI 时代我更看好三类：任务型写作、跨应用信息整理、垂直场景决策助手。它们共同点是结果可见、复用频次高。

这类产品以前卡在分发成本高。系统入口一旦放开，获客结构会变：口碑和留存的重要性会重新超过广告投放。

7）会不会买单
-------

过去一年我测过不少 AI 工具，最大的体感是：功能越堆越多，首用体验越容易卡住，留存就越难。苹果最擅长的，是把复杂能力藏进默认流程，让我不用记一堆开关。

如果 Siri 真变成“可调用多模型”的统一入口，我更在意你会不会觉得省事：你说得更顺、回得更快、结果能直接落到你正在做的事里。 你不用再打开不同 App 反复拷贝内容。 我更关心权限和数据怎么走，只要它仍按苹果的框架来处理，我更愿意把材料交给系统来完成。

这也解释了为什么我觉得这波调整值得等。等它真上线，你再看“顺手程度”就行，不用先纠结概念。

8）GPT Store 的教训
---------------

我回看 GPT Store 的争议，集中在两个痛点：开发者分析工具弱、变现机制不清晰。没有反馈闭环，开发者就像在黑屋里写产品。

苹果如果真想做成，至少要把这几件基础设施补齐：调用数据看板、明确分成规则、搜索和推荐机制透明、违规治理边界清晰。你可以把它理解成“AI 商店的水电煤”，缺一项都容易烂尾。

36 氪那篇旧文里提到一个对比我觉得很准：App Store 当年本质上是给开发者提供完整商业基础设施，不是只给一个“上架入口”。这句话放到今天依然成立。

9）抽成争议还会来
---------

只要是商店模型，抽成争议一定会来。问题不在于“抽不抽”，而在于“抽成和平台贡献是否匹配”。

我自己的判断是，AI 应用早期团队更在乎增长，不会把抽成放在第一位。因为这个阶段，先活下来比少交几个点更重要。

但到第二阶段就会变。等开发者有了稳定付费和品牌认知，关于分成、导流限制、交易透明度的矛盾会迅速上来，这几乎是平台经济的固定剧情。

10）品牌重心会变
---------

我以前写工具评测时，标题总喜欢放模型名字。最近慢慢改了，因为人真正记住的是“这个工具帮我完成了什么”，而不是“它底层用的是谁”。

系统分发一旦起来，开发者的品牌锚点会从“我们接了某某大模型”转向“我们在某个任务里最准最快”。这对产品经理是好消息，对只会蹭模型热度的团队是坏消息。

11）我最关心什么
---------

每次新平台刚开，官方发布会都很漂亮，真正决定生死的是文档和审核细则。比如：哪些能力可接入，哪些场景受限，数据怎么留存，调用失败怎么回退。

如果规则过严，生态会慢；如果规则过松，内容质量和安全问题会反噬。苹果过往的风格是先稳后放，所以我预期第一批可玩的空间不会太大，但会逐步扩容。

对创作者和从业者来说，盯住“规则更新日志”比盯住“发布会金句”更有用。前者决定你能不能做，后者只决定你想不想做。

12）现在能做什么
---------

我把这几天的判断落成了一个可执行版本，你不需要懂技术，照着做就能提前卡位：

先把你高频的 5 个重复任务写下来，比如“会议纪要整理”“长文改写”“行程规划”“资料汇总”“邮件润色”。这个动作看似笨，但它决定你后面选工具是不是贴身。

然后给每个任务设一个结果标准，不要写“更智能”，要写“3 分钟内出可直接发送的版本”这种可检验目标。没有标准，你永远在试工具，不会进入稳定工作流。

再做一次“系统内优先”测试：同一个任务，先用系统自带能力，再用第三方 AI，看谁步骤更短、结果更稳。你会很快发现，路径短一半，长期就能省下很多注意力。

最后留意 WWDC 后两类信号：一是是否真的出现 AI Extensions 分区，二是是否有明确开发者变现规则。前者决定叙事真假，后者决定生态死活。

阶段性结论
-----

如果你是普通人，你很快会感受到变化，但不一定记得背后是哪家模型。你真正会记住的是：这次终于少折腾，事一次做完。

如果你做产品，建议尽早从“做一个 AI App”切到“做一个可被系统调用的能力模块”。越像系统零件，越有机会留在下一轮。

⭐以上，既然看到这里了，如果觉得不错，随手点个赞、在看、转发三连吧，谢谢你看我的文章，我们下次再见。

[Claude Code 创始人最新15条技巧，看到这个帖子才知道自己只用了20%](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485063&idx=1&sn=890106467a11bfac22dee3dc171bb818&scene=21#wechat_redirect)

[突发！Anthropic前研究员私下流出内部提示词手册，处处是细节](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484999&idx=1&sn=afde19bf4f65c49f00e6e71971655699&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言