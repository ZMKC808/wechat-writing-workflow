     别再卷提示词了！Claude Fable 5发布后，顶级工程师都在搭循环 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

别再卷提示词了！Claude Fable 5发布后，顶级工程师都在搭循环
====================================

原创 阿竹 AI飞升录 2026-06-10 16:17 浙江

> 原文地址: [https://mp.weixin.qq.com/s/Or33BrQvVnvOZABOMRaJpA](https://mp.weixin.qq.com/s/Or33BrQvVnvOZABOMRaJpA)

![上传图片](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmccP5K6ND6JyEp875ic3V2kZ1vdxzwEbmKfamSIuls0MFkniaaDhUEUSft7CQDPF8FqiacY9fOAbl0zDeD5H8QUB23pdseIrYfRc/640?wx_fmt=png&from=appmsg)

Claude Fable 5 刚发布，能力遥遥领先，价格也离谱的贵，2小时烧光200刀会员额度。模型越强越贵，手写提示词的试错成本越高。这篇文章讲循环工程是什么、怎么搭、什么情况下不该搭。

Fable 5 和循环有什么关系
----------------

6月10号，Anthropic 发布了 Claude Fable 5。

先说背景。今年四月，Anthropic 悄悄发了一个叫 Claude Mythos Preview 的模型，被誉为超越 Opus 的第一个"神话级"模型。当时跟50家左右的初始合作伙伴找出了超过一万个高危或严重级别的漏洞，网络安全股全线暴跌。但 Anthropic 没公开——这个模型在网络安全领域的能力太强，怕被滥用。

两个月后，Fable 5 来了。它是 Mythos 的公开版本，加了一层安全分类器，所有人都能用。Fable 和 Mythos 是同一个底层模型，区别只在于 Fable 多了安全限制。

![Mythos vs Fable](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmWyrA7YLZ6QHY9zWicWBWF3tQ4xtky14BrM2CjOOpBV0sNah2ib0ThjylLLONSeRlXPCU9k53rxgZ3LpAoib3LLmAqnGHVZl2Y3s/640?wx_fmt=png&from=appmsg)

Fable 来自拉丁语 fabula，Mythos 来自希腊语，都是"被讲述之物"——寓言给所有人听，神话只在神殿里传颂。

能力有多强？几个例子：

•

Stripe 用它一天迁移了5000万行 Ruby 代码，这活一个人类团队干两个多月

•

它只看屏幕截图就通关了宝可梦火红，不看代码、不读地图、不用任何辅助工具，纯靠视觉

•

它自己做了一个基于浏览器的3D CAD 编辑器，然后用这个编辑器设计了一个可以3D打印的模型——工具的工具

•

有博主拿它给自己的项目做代码审查，1小时18分钟出了一个详细到"看了20分钟都没看完"的网页报告

贵到什么程度？每百万输入 token 10美元，每百万输出 token 50美元。200刀的 Max 会员额度，2个多小时就快烧光了。从6月22日起，Anthropic 会从订阅方案中移除 Fable 5，之后普通用户只能通过 API 按量付费。目前有一个12天的免费窗口。

模型越强，手写提示词的试错成本越高。你舍得拿 Fable 5 一轮一轮地猜提示词吗？

死胡同
---

我用AI写代码的方式，过去两年基本没变过：写一段提示词，等它返回，看一眼，再写一段。每次都在重新告诉它我在干嘛、我想要什么、上次改了什么。

**提示词本身是手动劳动。**

你写一个提示词，AI返回一个结果。你读结果，写下一个提示词。你是整个回路里唯一的决策者、唯一的审查者、唯一的记忆。每次对话结束，上下文清空，下次从零开始。

这件事的根源在于结构：你用的是一个没有记忆的系统，你就是那个记忆。

Anthropic 负责 Claude Code 的 @bcherny 说了一句很准的话："我不再给 Claude 写提示词了。我有循环在运行，它们给 Claude 发提示并决定下一步做什么。我的工作是写循环。"

什么是循环工程
-------

@steipete 也说过类似的话："你不应该再亲自给编码Agent写提示词了。你应该设计循环，让循环来给你的Agent发提示。"

什么意思？

过去你是一对一：你写提示词，AI执行。现在你设计一个系统：它自己发现任务、分配任务、检查结果、记录进度，然后决定下一步。你设计一次，它自己跑。

Addy Osmani 把这个叫「循环工程」。他在 agent harness engineering（为单个智能体运行的环境做工程化）和 factory model（构建软件的系统）的基础上，又加了一层。循环工程位于运行框架上面一层——它像运行框架，但会按定时器运行，会生成小助手，并且会自我驱动。

![HKYTPjUX0AAJooq](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zn6Rxial4KMQK5Yib3pW4FzQnXHe0dfu949zDrEtEB46zbdVAV1iaZriaSibMZybKQa7nh4vDqxZujoLKhalykibqF91eG0iaY6nAQgfQ/640?wx_fmt=png&from=appmsg)

Anthropic 工程师现在每天合并的代码量是 2024 年的八倍——Anthropic 自己称这个数字"几乎肯定是真实生产率提升的夸大说法"。数字有争议，机制很清晰： **杠杆从输入提示转移到了设计提示的循环。**

四个条件
----

在你兴奋地开始搭循环之前，先想清楚一件事。循环在四个条件下才能收回成本。错过任何一个，循环的成本就会超过它带来的收益。

![HKYVILFW0AAmsCm](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmdelm8QhbDI1IbGdy1SKicsdl2trNvia03BNX9Mmzu1qtQeq9IY3Bwib6q0XtADaWJ2QyRansYqGewaHvvkJ0aasFzicoOlChEdmE/640?wx_fmt=png&from=appmsg)

**任务得重复。**  循环的价值来自多次运行摊销设置成本。一次性任务，一个好的提示词更快更便宜。如果工作不会每周重复，你不需要循环——你只需要跑一次的脚本。

**验证得自动化。**  循环需要一个不需要你参与就能判错的东西。测试套件、类型检查、lint、构建。没有自动检查，你就得坐回去读每一个diff——这正是循环本应去除的工作。

**token预算得撑得住。**  循环会重新读上下文、重试、探索，不管跑出来有没有结果都烧token。Claude Fable 5 每百万输入10刀、输出50刀，跑循环的成本比Opus时代高一个数量级。对拥有免费token的人来说这显而易见，对按量计费的人来说得认真算账。

**Agent还得有工具。**  日志、能复现的环境、能跑自己写的代码。没有这些，循环就是在黑暗中瞎迭代。

四个条件缺一个就不该建。 **大多数开发者目前不需要循环。**

### 30秒循环检查

四个条件是战略判断。在把具体任务转成循环之前，还有一个战术清单。 **漏掉一个就保留为手动提示。**

1.

该任务至少每周发生一次。少于每周，设置成本永远无法摊销。

2.

一个测试、类型检查、构建或lint可以拒绝不良输出。没有自动门控，Agent自己给自己打分。

3.

Agent可以运行它修改的代码。没有可复现环境，迭代就是盲的。

4.

循环有硬性停止条件——token预算、迭代次数或时间限制。没有这些，循环会一直跑到你注意到账单。

5.

合并、部署或依赖变更前需人工审核。任何不可逆的操作都需要人批准。

### 谁赢，谁输

经济规律不是普遍适用的。觉得循环工程显而易见的人，通常有无限制的token。觉得这是鲁莽行为的人，通常用每月20美元的消费套餐。

真正受益的人：

•

**有重复性、机器可检查工作且预算充足的团队。**  持续测试筛选、依赖调整、代码风格检查与修复、在测试覆盖率强的代码库上从issue到PR的草稿。

•

**有强测试套件的代码库。**  如果初级工程师能根据清单完成任务，测试套件能捕获他们的错误，循环就适用。

•

**已采用多智能体模式的异步优先团队。**  对这些团队，流程是缺失的编排层。

今天应该跳过的人：

•

**个人用户在消费级计划上。**  效率提升往往先于token账单到来。

•

**缺乏自动验证的人。**  没有实际检查的循环，就是Agent在重复中自我达成一致。

•

**评审能力是瓶颈的团队。**  循环会生成更多代码；如果评审已经是瓶颈，它只会让队列更长。

对于一次性任务、探索性工作，或任何"完成"需要主观判断的情况， **一个精准的提示词仍然胜出。**

五个构件
----

一年前想要一个循环，你得写一堆Bash脚本，然后永远维护那堆东西。现在 Claude Code 和 Codex 都把核心组件内置了。

![HKYT-XBXEAI0yYt](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlBsWndrcQdNwQhDK3B4GljDMmHSV4c3PYe5QMvtfxK6nnIy51TDT5MQBvu2tpbQu2RbUkpbdPTlECbicOkFvNxxauicJY1C57cE/640?wx_fmt=png&from=appmsg)

循环需要五个构件，再加一个能记住状态的地方。

### 自动化

自动化是循环和一次性手动任务的分界线。

Codex 里叫 Automations——选一个项目，设提示词，选节奏，选本地检出还是后台工作树。找到内容的运行进入筛选收件箱，没找到的自动归档。OpenAI 内部也用它处理重复性工作：每日issue分拣、CI失败汇总、提交说明撰写、排查近期新增bug。

Claude Code 用  `/loop`  和 cron 达到同样效果。 `/loop`  按固定频率重新运行， `/goal`  持续运行直到你写的条件为真。关键区别： `/goal`  每轮结束后由一个独立的小模型检查完成情况，写代码的Agent自己给自己打分的情况被规避了。你给它条件"All tests in test/auth pass and lint is clean"，然后就可以走了。

![HKYY3V-WkAAiB-j](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zneEIW8RjNnCxIAS53Db9jemRq1REsUxwGohb0GkJLakz3p5FGDyaARhibvcRsIdzJkpEXoGn0IsicJ786ibiaiaicSlNvOCfAxoWibdk/640?wx_fmt=png&from=appmsg)

    > /loop30m /goal All tests in test/auth pass and lint is clean.  Scan src/auth fornew failures, propose fixes in claude/auth-fixes,open draft PR when goal condition holds.  CronCreate(*/30 * * * * : auth quality loop)  Stop condition: tests pass + lint clean (verified by checker)  Scheduled. Will continue past intermediate completionsuntil /goal condition is met by independent checker.

自动化还能调用技能，让周期性任务更易维护——直接引用技能名称，省得把冗长指令粘贴到定时任务里然后永远不更新。

### 工作树

两个Agent同时改一个文件，跟两个工程师不沟通就往同一行代码里提交一样。Git worktree 让每个Agent在自己的分支上干活，共享同一个仓库历史，一个Agent的编辑字面上不会触及另一个的检出。

Codex 内置了worktree支持。Claude Code 用  `--worktree`  标志在独立工作目录里开会话，子Agent设  `isolation: worktree`  每个助手自动获得独立检出并用后清理。

但说实话，工具能解决文件冲突，解决不了你的审查瓶颈。你能同时审几个Agent的产出，才是真正限制你的东西。

### 技能

这是我最看重的。Agent每次启动都是冷启动，你不说它就猜。技能就是把你的意图固化下来：构建步骤、约定、"因为那次事故我们不这样做"。写一次，每次运行都读。

两个工具用同一个格式：一个文件夹，里面有 SKILL.md，保存指令和元数据，外加可选的脚本、参考资料。Codex 用  `$`  或  `/skills`  调用技能，也会根据任务描述自动匹配——这就是为什么一个紧凑准确的描述，远胜过花里胡哨的描述。

没有技能，循环每轮都从零推导你的项目。Agent每次会话都是冷启动，它会用自信的猜测来填补你意图中的任何空白——约定、构建步骤、"因为那次事故我们不这样做"，这些写一次在外部，每次运行都读，才能复利。

有一点要分清：技能是编写格式，插件是分发方式。跨仓库共享技能时，打包成插件。

### 连接器

只能看到文件系统的循环是一个微小的循环。基于 MCP 的连接器，让Agent能读你的问题追踪器、查数据库、发Slack消息。Claude Code 和 Codex 都支持 MCP，一个工具写的连接器另一个也能用。

![HKYZ6H9XEAA54ks](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmVjYibia1OkWgwO8RB0hXfMceEbYlCbicc4Xm74XWmejOMEwgY4CuCNmgQcIzvys8jFNqDQuHHGOPgCMExUEek6RocakbSbtyVRM/640?wx_fmt=png&from=appmsg)

连接器让循环在你的真实环境里行动——打开PR、关联工单、CI通过后通知频道，光说"如果我能做我会怎么做"的Agent跟没说一样。

回报最快的连接器，按顺序：

1.

**GitHub**  — 读仓库、建分支、开PR、评论issue、响应webhook。第一天最大的收获。

2.

**Linear或Jira**  — 循环推进时更新工单，PR链接到issue，验证通过时自动关闭。

3.

**Slack**  — 发事后处理结果，升级事件中@人，早上总结夜间运行。

4.

**Sentry/错误追踪器**  — 让循环调查实时警报，为高频警报草拟修复。

### 子Agent

最重要的一个。写代码的Agent给自己打分太宽容了，你得让另一个Agent来检查。

![HKYaufLXEAAgTCz](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zn5beQlbALg245fUzhVCNpft3k6Ias7gvxqMseVww0rGh5ic5a3kriaO9uDtiaHZ0LibbOibKDVzrDFB9l7icdXibjc8ibMTC9z0Ycmw40/640?wx_fmt=png&from=appmsg)

Codex 只在你要求时才生成子Agent，同时运行，然后把结果折叠回一个答案。你可以在  `.codex/agents/`  里用 TOML 定义自己的Agent——名称、描述、指令、可选的模型和推理强度。安全审查者可以是高推理强度的大模型，探索者可以是快速只读的东西。

Claude Code 在  `.claude/agents/`  里做同样的事。分工通常是：一个探索，一个实现，一个验证。子Agent烧token，但烧在值得的地方。

`/goal`  的设计也遵循同一逻辑：一个全新的独立模型负责判断循环是否终止，执行任务的本体模型只管干活——"执行者+校验者"的分离直接应用到了停止条件上。

### 记忆

一个 Markdown 文件，一个 Linear 看板，任何活在单次对话之外、能保存"做了什么"和"下一步"的东西。听起来太简单没啥技术含量，但所有长期运行的智能体都依赖同一个技巧：模型在两次运行之间会忘掉一切，记忆必须存在磁盘上。

状态文件长什么样：

    # Loop state · ci-triage## Last run2026-06-09 03:30 UTC · 7 failures classified, 3 fixes drafted, 4 escalated## In progress- claude/fix-auth-token-refresh — tests passing locally, awaiting CI- claude/fix-flaky-payment-webhook — retry pattern applied, monitoring## Completed today- claude/bump-axios-1.7.4 → merged (CI green, deps loop verified)- claude/lint-fix-pass-june-9 → merged## Escalated to humans- src/billing/refund.ts — tests failing in 3 ways, root cause unclear- ci/staging-runner — infra timeouts, not a code issue## Lessons learned- 2026-06-08: PowerShell hits TLS 1.2 issue on this Windows runner. Use bash.- 2026-06-07: tests/e2e/checkout requires Stripe webhook secret in env. Skip if missing.

两种存放模式：仓库里的Markdown文件，简单、版本控制、支持diff；或者外部系统（Linear、GitHub Issues），跨仓库持久、支持查询、团队可见。对长期运行的循环，把状态文件和固定的顶层规格（VISION.md 或 AGENTS.md）配合使用——状态文件告诉Agent它当前在哪，规格文件告诉它应该往哪走。

最小可行循环
------

如果你过了四个条件的测试，先搭能工作的最小循环。四个部分，没有花活。

![HKYbR9NXcAAfivV](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9znA1ic3JZ4zZs3AXqG0j18otxnK5erKt8LMwolrNE4Aq0hG1Z5Efm4fJSxK1XvZFZAmWLGnG2gExPnP1prMianZXNT3G81PA5Upg/640?wx_fmt=png&from=appmsg)

**一个自动化。**  一个按固定频率触发并在明确条件下停止的定时运行。

**一项技能。**  一个 SKILL.md 文件，存Agent每次运行时原本需要重新推导的项目上下文。

**一个状态文件。**  一个 markdown 或 Linear 板，记录已完成和下一步。第二天接着跑，不用从头来。

**一个门控。**  一个测试、类型检查或构建，自动拒绝劣质工作。没有门控，循环只是在烧token。

顺序很重要：先确保手动运行是可靠的，把它变成技能，用循环包装，然后安排定时。跳过步骤是循环失败的根源。

值得关注的指标是 **每项接受变更的成本** ——token数量和尝试的任务数都不重要，接受变更率低于50%说明循环在失去价值。

### 好循环 vs 坏循环

好的起点：

•

**CI失败分诊**  — 每晚扫描失败，分类原因，为简单问题草拟修复PR。

•

**依赖更新PR**  — 每周检查更新，测试兼容性，打开PR。

•

**检查并修复**  — 每次开PR时自动应用样式修复。

•

**不稳定测试重现**  — 循环直到一个理论通过测试。

•

**issue到PR草稿**  — 在测试覆盖率强的代码库上，不良输出会被测试套件拒绝。

不该碰的：

•

架构重写

•

认证或支付代码

•

生产部署

•

模糊的产品工作

•

任何"完成"是主观判断的工作

拉尔夫·威格姆循环
---------

循环有个特别恶心的失效模式，有个名字叫「拉尔夫·威格姆循环」。

工程师格雷戈里·亨特利记录了这种模式：一个Agent本该在完成时才标记完成，但它过早宣布"搞定了"，循环在一个未完成的任务上退出。没有硬性停止条件的话，循环会安静地失败，继续烧Token，而你以为它在干活。

什么时候会出现？

•

**没有真正的验证者。**  只是让第二个Agent"审查"，没有客观信号，两个乐观主义者互相点头。

•

**软性完成条件。**  "完成"由Agent的主观判断定义，测试和构建都没有参与。

•

**没有硬性停止。**  循环一直跑到外部因素终止它——速率限制、或者你终于注意到。

修复方法：加一个客观的、能让工作失败的东西。一个通过或失败的测试。一个能编译或不能编译的构建。得有硬信号，靠主观意见的验证器救不了你。

![HKYYGruWIAAWmLC](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9znR8JS41K9vBuCCzNIuUd7ywjyxibXBJsNArGv739uuxyicUcsDdENGf0V0TeCIEEriaOq5Bfmx7LLzGb4MUg5MR0BntNiatFfrzBw/640?wx_fmt=png&from=appmsg)

还有几个值得知道的失效模式：

•

**目标漂移。**  每一步的总结都有损失；"不要做X"的约束在第47轮时消失了。缓解：每次运行时重新读 VISION.md。

•

**自我偏好偏见。**  写代码的Agent对自己作业评分太宽松。缓解：独立验证子Agent，不碰创建者的推理。

•

**代理式懒惰。**  循环在部分完成时声明"够了"。缓解： `/goal`  + 客观停止条件。

循环会让你变蠢
-------

随着循环变好，有两个问题反而更尖锐。

循环交付你没写过的代码越快，你对系统的理解就越模糊。真正让你痛苦的那一刻，是团队里没人读过的系统需要你调试的那一天。这叫理解债务。

另一个更隐蔽的问题：循环自己跑的时候，你很容易停止判断，接受它返回的一切。我有时候也会这样——跑完了一看结果挺像样的，就直接用了，也没仔细看它到底改了什么。跟自动驾驶一个道理，你越信任它，就越不看路。

缓解方法靠的是纪律：

•

**读diff。**  不读循环提交的内容，就是以复利的方式积累理解债务。

•

**检查门控。**  挑几个循环打开的PR，验证批准它们的测试是否真的捕获了你关心的失效模式。门控用久了会失效，定期验证。

•

**别让循环碰架构工作。**  保持它在小范围内、机器可验证的变更。一旦让它触及判断，理解债务就加速。

•

**配对设计循环。**  第二双眼睛能捕捉循环将永远利用的盲点。

两个人可以搭完全相同的循环，得到截然相反的结果。一个人用它在自己深刻理解的工作上更快推进，另一个人用它完全避免理解工作。循环不知道区别。你知道。

安全税
---

无人看管的循环也是无人看管的攻击面。

你的循环必须防御的威胁：

•

**未经审查的代码发布。**  循环提交的PR比人阅读的速度快。没有安全检查（SAST、依赖审计、密钥扫描）的门控，不安全的代码会自动合并。

•

**技能作为注入向量。**  自动安装技能的循环会继承其描述中隐藏的每个提示注入。安装前审计技能来源。

•

**日志中的凭证。**  长时间运行的循环中调试日志会把密钥散到你未监控的日志里。生产循环禁用详细日志。

•

**权限范围蔓延。**  用只读权限测试的循环为了方便加"仅一个"写权限，然后从未重新审计。每30天重新审计权限。

杠杆点转移了
------

Cherny 说的核心就一件事：杠杆点转移了。

以前你的价值在于写好的提示词。现在你的价值在于设计好的系统。以前你是操作员，现在你是架构师。

循环设计比提示词工程难得多。

先别急着搭循环。先想清楚你重复在做的事情是什么，能不能自动化验证，token预算撑不撑得住。四个条件过了，从最小循环开始——一个自动化、一项技能、一个状态文件、一个门控。让手动运行先可靠，再包装成循环。

搭循环吧。带着工程师的判断力去搭，别只当那个按"开始"按钮的人。

Fable 5的免费窗口还有不到两周。与其拿它一轮一轮猜提示词，不如花一天搭个最小循环，让它自己跑起来。

⭐如果你希望下次也能接受到此等质量的好文 请务必将我们星标，防止迷路！转给你的亲友一起变强！

> 关注「AI飞升录」，回复「进群」加入飞升社区。

[（虾）瞎做的号，被AI媒体top1签约了](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485876&idx=1&sn=c93ed7401ef8c09d96bc124130a32a94&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言