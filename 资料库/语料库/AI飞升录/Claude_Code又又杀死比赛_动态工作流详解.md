     Claude Code又又杀死比赛，动态工作流详解 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

Claude Code又又杀死比赛，动态工作流详解
=========================

原创 阿竹 AI飞升录 2026-06-05 10:31 浙江

> 原文地址: [https://mp.weixin.qq.com/s/Uy49npmlqPi1cWqhii--eg](https://mp.weixin.qq.com/s/Uy49npmlqPi1cWqhii--eg)

> Dynamic Workflows上线两周了。一个workflow能替代50个手动prompt，但大多数用户还没用过。

5月28日，Anthropic在Claude Code里上线了Dynamic Workflows。

简单说：你给Claude一个任务，它自己写一个JavaScript harness，拆成多个独立Agent，各自带上下文窗口和模型选择，然后协调完成。

用过的人有个共同感受，以前是你设计好流程让AI跑，现在AI自己设计流程。

![为每项任务打造专属工具](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmbRyBUXUKOnSplEltKUC9iavfIiaunvrRHxPlgQK9rdE6VYeHxR9lshUDYEFBqSmMAxlMia0WzoMtTS5swqjdGftucIcmG11GdXc/640?wx_fmt=png&from=appmsg)

工具易手
----

回头看这两年，有个脉络很清楚。

最早是Prompt Engineering，人写说明书，AI照着做。说明书越聪明，结果越好。后来是Agent编排，人画流程图，多个AI按步骤跑。再后来是MCP，人造好一堆工具，AI学会挑着用。

每一步，造工具的都是人。AI只管用。

你雇了个天才员工，但锤子得你提前造好、分类放好、写好使用说明，他才干活。Dynamic Workflows把这事翻过来了：你跟他说"把这面墙拆了"，他自己判断需要什么，自己造锤子，甚至造个机器人帮他一起拆。

窗口之困
----

一个Claude在一个窗口里做所有事，简单任务没问题。复杂任务迟早踩坑。

**Agent偷懒。**  审查50个文件，处理20个就宣布全部完成。不是故意的，窗口里代码和工具返回越堆越多，注意力被稀释，工作记忆耗完，后面的就选择性忽略了。你查不出来，因为报告看着挺完整。

**自我偏好。**  让生成代码的Agent同时审查代码，它天然信任自己的推理逻辑。就像让一个学生给自己打分，利益相关的裁判不可能公平。

**目标漂移。**  对话到第47轮，"不要做X"这种约束悄悄消失了。Claude Code底层会做有损的上下文压缩（Compaction），每次摘要都在丢信息。边界条件、否定约束，最容易被当成冗余扔掉。

这三个问题的根源一样：一个人干所有事，这件事本身有天花板。法官不兼任律师，审计师不兼任会计，分工不是为了好看，是结构性地解决问题。

动静之别
----

你可能用过 `claude -p` 或Claude Agent SDK构建静态工作流，协调多个Claude实例。

静态工作流是通用的，写一次，覆盖所有边缘情况。能用，但必须保守。

动态工作流不同。Claude会为"这一个任务"编写"这一个workflow"。

![静态 vs 动态](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zlzEXbHdJ8VL8vJibFKJpxEaL5Fic1MGNnuMtr35EVfjjYmgbiaAHH5HjmMFxicmMPFooRGU5LZUw9iaibDkHKkVfKic7ib4icsoYyoUMz8/640?wx_fmt=png&from=appmsg)

差异不在于搜索步骤本身，两者都能搜。真正的差异在于workflow能围绕你的上下文塑形，读你的代码，对照真实文档检查每个feature，按你的场景估算成本，然后对自己的答案跑一轮对抗性验证。静态harness做不到，因为它不知道你的代码长什么样。

更关键的区别：静态工作流的控制权在"概率性的模型"手里，动态工作流的控制权在"确定性的代码"手里。循环、分支、条件全部由JavaScript逻辑物理锁定，不会因为模型的一次概率偏离就跑偏。

三个函数
----

Dynamic Workflows的本质是一段由Claude即时编写并执行的JavaScript脚本，运行在本地沙箱环境里。它不仅支持JSON、Math、Array等标准JavaScript功能，还注入了三个核心函数。

理解它们，就足够读懂Claude为你写出的任何workflow。

![三个核心函数](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9znn0JNmCLKjJVIdIWdMIdriaz3f2tuBjn3MCAKyz7bMicVT6BML1wJ9TwFgqsIgGq3x0bgoYrAicHufcxVaF0EXYWI405xGJAWces/640?wx_fmt=png&from=appmsg)

`agent()` 启动一个独立Agent。指定模型（Opus做困难推理，Haiku做低成本探索）、目标、隔离级别。每个Agent有自己独立的上下文窗口，互不污染。还能通过JSON Schema强制输出结构化结果，方便后续代码解析。

`parallel()` 并行执行，所有人到齐才开饭。适合需要全局去重或统一集成的场景。

`pipeline()`  流式处理，不等人。文件A进入阶段三的同时，文件B可能刚进阶段一。更便宜更快。

选哪个？看你是否必须拿到所有结果才能做下一步。是，用parallel。否，用pipeline。

六种模式
----

Anthropic工程师在研究、代码审查、迁移重写中总结出来的，不是纸上谈兵。

![六种模式](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zluBkIice2bYfGWBGwUm2yFJQAiaRCWaCQHVETicKwBgu1hO3MOGhdhQDbU4A8iaQvykCgWmDOTXy24KaXHUMZ5SuQlOGUiaiayGgI6k/640?wx_fmt=png&from=appmsg)

**分类再执行。**  先判断任务类型再路由。比如"解释auth模块怎么工作"，classifier先读代码估算复杂度，10个文件用Sonnet，100个文件用Opus。先搞清楚工作量，再决定投入。

**扇出再综合。**  实践中用得最多。任务拆小，每个步骤一个Agent并行跑，最后合并。每个subagent只看自己那一块，不会被无关细节干扰。

**对抗性验证。**  写代码的Agent和审代码的Agent必须分开。verifier只看评分标准和产出物，不知道是谁写的，否则自我偏好会通过prompt暗示渗回来。

![对抗性验证](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9znRj14FpolCd7weot3eXcCayF7pQpb6VxpXw3CybDickFRQcYymSZjeodNxCQHJIaHibTliaM3xBI6ciaY6bjtXsJiaVrLsQfVMzjts/640?wx_fmt=png&from=appmsg)

**生成再过滤。**  先批量出方案，再用评分标准淘汰。比如起产品名，生成30个，过滤掉陈词滥调和商标冲突，留3个。直接问"最好的名字是什么"会让AI过早下注，先让它多想再筛选更靠谱。

**锦标赛。**  多个Agent用不同方法做同一个任务，两两比较决出胜者。比较式判断比绝对评分可靠得多，给1000个item打分，质量会下降且上下文装不下。锦标赛每次只比较两个，公平且隔离。

![锦标赛](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlNICayWFSQiaBGCeuLJ86Waqgic4IpKuk4eHynGKMun3l184wQMqjrKTy4lriczCzD6akITWF20CiaPbXboxicHuu8ticVAyIEa7Xbg/640?wx_fmt=png&from=appmsg)

**循环直到完成。**  工作量未知时，不设固定轮数，跑直到满足停止条件。持续找bug直到一轮返回0个问题，复现flaky test直到某个理论成立。停止条件写在代码里，不靠模型自己判断。

![使用场景](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlJSVpU8ZLJk8kxqj2l3xA7GO9r6D4FsfGcCQ1IibzE5mDN4dLNzfI7MdMp5ZCSavEeTaAjKQdUPHeD9ia0jsjyZtaS8M7BIDhEI/640?wx_fmt=png&from=appmsg)

Bun重写记
------

Bun的创始人Jarred Sumner公开分享了他们用Dynamic Workflows重写的过程。

方法：把重写任务拆成调用点、失败测试、模块。上百个文件分别建worktree分支，每个分支里一个subagent并行重写逻辑，另一个Agent做对抗性审查，最后在主分支合并。一个AI写修复，另一个AI审修复。

上下文税
----

单窗口串行执行有个隐藏成本：输入Token随步骤增加呈二次方级暴涨。这叫"上下文税"。

每一步，模型都得把之前的工具返回、思考历史、代码片段全部重新读一遍。到第15个执行回合，哪怕只输出一个字符，也得先付10,000个Token的门票。

动态工作流把大任务切碎成短命的并行子会话。每个子代理通常只跑1到3轮，输入Token锁在低位。表面看workflow消耗更多token，实际它避开了二次方膨胀。

但要注意：Loop-until-done模式下，如果子代理遇到怪异的依赖死锁，它可能会固执地尝试10种不同方案，反复调用高成本模型。一次失败任务吞噬的token，可能比成功运行高出5倍。

模型分级
----

默认workflow把所有子代理都绑在最贵的Opus上。读个文件路径、跑个lint，都在烧顶级模型的钱。

在workflow脚本里可以显式分配模型：全局规划用Opus，代码实现用Sonnet（成本降80%），跑lint和单测用Haiku（降95%）。

![记忆和规则遵守](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmkOFWZ1xakpyVdeLO6BlhAfzYFBiaicIsBwU2ZAGym4Hck5YRHaOSnNhkcr93jpxptWmibHoLgNOzaoraSjHXT7SpWUH9khSsicdw/640?wx_fmt=png&from=appmsg)

成本控制
----

配合 `/goal` 设定硬性完成要求，workflow不会在软性完成点提前停。配合 `/loop` 可以让整个workflow按固定周期跑，适合持续分诊。还可以在prompt里直接设token预算，"use 10k tokens"，没上限的话，workflow可能膨胀到预期的5到10倍。

角色之变
----

你的工作从"写prompt"变成了"设计workflow"。告诉AI"要什么"，它自己决定怎么做。

类比一下：手写汇编 → 高级语言 → 框架 → AI写代码。每一步，人都往上走一层，把执行层让给机器。Dynamic Workflows是这条路上的又一步，但让出去的层级更高了，连"设计执行方案"这件事本身，也开始交给AI了。

输入隔离
----

任何读取不可信公开内容的工作流（support tickets、bug reports、用户反馈、抓取数据），都需要假设这些内容可能包含prompt injection。

解决办法：禁止读取不可信内容的Agent执行高权限操作。由另一组没有接触原始内容的独立Agent执行动作。

如果输入不是你写的，就隔离它。一个只读的reader agent几乎没有成本，却能移除一整类prompt injection风险。

何时不用
----

大多数传统编码任务不需要workflow。先问自己：这个任务真的需要更多计算能力吗？常规Claude Code session能在五分钟内完成的，不需要workflow。

不要为了用而用。5个reviewer组成的panel听起来很酷，但如果你只是改了个bug，杀鸡不需要牛刀。

保存和复用
-----

workflow跑通之后，在workflow菜单里按 `s` 保存。文件放到 `~/.claude/workflows` 。

可以打包成Skill发布：把JavaScript文件放到Skill文件夹，在SKILL.md里引用。任何安装这个Skill的人都能运行同一个workflow。

实用技巧：提示Claude把Skill里的workflow当模板而不是脚本，让它根据当前任务调整workflow形状，同时保留整体结构。

实战prompt
--------

> "这个测试大约每50次运行中会失败1次。创建一个工作流来复现它，提出假设，并在工作树中对抗性测试它们，直到找到有效的理论。"

> "使用工作流，回顾我最近50次会话，挖掘我反复犯的错误，将反复出现的错误转化为CLAUDE.md规则。"

> "拿我的商业计划书，运行一个工作流，让不同的Agent从投资者、客户和竞争对手的角度对它进行剖析。"

> "这里有80份简历的文件夹，使用工作流为后端职位对它们进行排名，并对前十名进行双重检查。"

尾声
--

Prompt Engineering是造说明书，Agent编排是造流程图，MCP是造工具箱。Dynamic Workflows把这些事翻过来了，AI开始给自己造工具。

你不用提前设计好所有流程，不用预判边缘情况，不用为每种任务写专门的harness。告诉它要什么，它在运行时为这个具体任务生成具体的解决方案。

动态工作流在2026年5月28日随Claude Code发布。Anthropic官方博客原文中文精译PDF，公众号回复「工作流」领取。

⭐如果你希望下次也能接受到此等质量的好文 请务必将我们星标，防止迷路！转给你的亲友一起变强！

[速薅！200刀的Pro 20x，978块拿下](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485753&idx=1&sn=49f9b35d6b93b4322c516a6c333335d3&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言