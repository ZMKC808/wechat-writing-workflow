     Claude Code 创始人最新15条技巧，看到这个帖子才知道自己只用了20% \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

Claude Code 创始人最新15条技巧，看到这个帖子才知道自己只用了20%
========================================

原创 阿竹 AI飞升录 2026-03-30 14:51 浙江

> 原文地址: [https://mp.weixin.qq.com/s/XO8FDpMD8zxoFkvnW-tHAw](https://mp.weixin.qq.com/s/XO8FDpMD8zxoFkvnW-tHAw)

  

![](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlEgbd4aGBJAscE16xczIMmgtticlicL91GXIcKeMQMOunme8cfzgrD3242F2gHRdaXTn5KDvxN3fFT08Sqhu857YOL0wk0YGtL8/640?wx_fmt=png&from=appmsg)

今天刷到一条帖子，发帖的是 Claude Code 的团队成员 Boris Cherny。他列了15条自己日常在用的技巧，每条都带具体操作方法。

我看到第三条就坐不住了——他在本机同时跑着好几个定时任务，每5分钟自动处理代码审查，每30分钟自动整理反馈。我用了三个月 Claude Code，完全不知道还能这么干。

从头到尾看完，我整理了15条，按我自己的理解重新讲一遍。有些功能我已经试了，有些还在观望，会标清楚。

手机端写代码：他真的在手机上用 Claude Code
---------------------------

Boris 说他很多代码是在 iOS App 上写的。

这个功能藏在 Claude App 里，左侧切到 Code 标签页就能看到。iOS 去年10月就集成了，Android 今年初跟进。手机上肯定没法做复杂的编码，但用来看看任务进度、给一个跑了半小时的会话追加一句指令、通勤时处理个简单任务，够了。

不过要注意一点：手机端目前不能凭空启动一个全新的 Code 会话。它更多是配合下面要讲的 Remote Control 用的——控制你电脑上已经在跑的会话。

下载 Claude iOS/Android App，左侧 Code 标签页就是入口。

Remote Control + Teleport：会话跟着人走，不跟着电脑走
---------------------------------------

**Remote Control**：终端里输 `claude --remote-control` 或者打 `/rc`，屏幕上弹出一个二维码。手机扫一下，就能在 claude.ai 或 Claude App 上实时操控这个会话。会话始终在你的本地机器跑，手机只是个遥控器。

**Teleport** 反过来——把 Web 端的云端会话拉到本地终端继续。输入 `claude --teleport` 或 `/teleport`，它会自动验证仓库状态、切换到远程会话的分支、加载完整对话历史。只能从 Web 拉到本地，单向的。

![Remote Control 远程控制示意图](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9znRmg4n33oC37vdicDpGfW8VibRM6ezia2BpUicH342kF3calyHWkmkfowZia4nBKyRwPnpcL8zTvic8zZKia78ag64PhMEzmQJias1ibAk/640?from=appmsg)

Boris 说他直接在设置里开了「Enable Remote Control」，默认始终开启。

一个实际场景：你在公司电脑上启动了一个重构任务，下班路上用手机 Remote Control 看进度、批准权限请求、追加指令。到家后在个人电脑上 Teleport 把会话拉过来继续。

还有个更具体的：长任务跑到一半需要你审批权限（比如要不要执行某个危险命令），你不在电脑前怎么办？以前只能等回去再说。现在 Remote Control 可以把权限请求转到手机上，地铁里就能批。2月25日发布的，v2.1.58版本。

/loop 和 /schedule：他说这是最强大的两个功能
------------------------------

Boris 原话就是"最强大的两个功能"。他自己跑着一堆自动化循环：

    /loop 5m /babysit — 每5分钟自动处理 PR 评论、自动 rebase、自动回复 review /loop 1h /tidy — 每小时自动清理代码库需要维护的东西 /loop 6h /dep-upgrade — 每6小时自动升级依赖并提 PR 

两个命令的区别：`/loop` 是在当前命令行会话里循环执行，退出会话就消失，创建后3天自动过期，单会话最多50个。`/schedule` 是创建持久化的定时任务，在桌面端的 Cowork 里管理，重启后还在跑。

怎么选？短期监控用 `/loop`（比如盯一小时的部署），长期自动化用 `/schedule`（比如每天早上跑测试）。3月7日发布，v2.1.71版本。

![/loop 和 /schedule 自动化任务流程](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmeLx1GlS2S4r76kYIjwSRQv2LYSA89BVSVvYtPg43AENcw7ACzDeDmV48sXH5FYtshoNATu04bGL3oLWsxhGFzMNfA4A5UxEI/640?from=appmsg)

我试着想了一下这件事：每5分钟自动检查一次 PR 评论。你提交 PR 后不用再盯着了，Claude 会自动回复 reviewer 的评论、自动 rebase 冲突、自动跑 CI 修错。说白了这不是工具了，是一个不下班的同事在帮你值班。

`/schedule` 更厉害。你可以设一个每天早上8点自动跑的任务：「检查所有 open 的 issue，把 P0 的整理成列表」。哪怕你电脑关了也能跑，因为它在云端执行。

Hooks：在 AI 干活的每个节点插入你自己的规矩
--------------------------

Boris 举的例子：

*   **SessionStart**
    
    ：每次启动 Claude 时自动加载上下文
    

*   **PreToolUse**
    
    ：记录 Claude 执行的每条 bash 命令
    

*   **PostToolUse**
    
    ：代码写完自动跑 lint 和测试
    

他还提了个骚操作：把权限请求路由到 WhatsApp，在外面就能远程审批。

Hooks 不算新东西了，但这几个月变化很大。现在有25个生命周期事件，从 SessionStart 到 WorktreeCreate 全覆盖，支持正则匹配工具名，配置文件分全局、项目、本地三个层级。

![Hooks 生命周期系统](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zlG1micuOqPKW6ib5ntxHcyrCC6IWgdGHHUODlUUFPAcWN76sebuYL9hAiaIJSatmpGeMFEocfX1bNNSMAxmmAYxfxrxsOR0yMehE/640?from=appmsg)

我的理解是这样的：把它想成 CI/CD 的本地版。CI 是代码提交后的自动化，Hooks 是代码生成时的自动化。AI 写完代码 → 自动跑 formatter → 自动跑测试 → 测试不过就自动修。整个链条不需要你盯着。

官方文档：https://code.claude.com/docs/en/hooks

Dispatch：不在电脑前也能干活
------------------

Boris 说他每天都用 Dispatch 来处理 Slack 和邮件、管理文件。不写代码的时候，他就在 Dispatch。

Dispatch 是 Claude 桌面应用里的一个功能，在 Cowork 标签页里。你给它发一条消息描述任务，它自己判断怎么处理：编码任务（修 bug、跑测试、提 PR）自动开一个 Code 会话；调研、文档、表格类工作在 Cowork 里处理。

有意思的是——你可以从手机发任务给 Dispatch。它在你的电脑上执行，完成后推送通知到手机。3月17日发布的 Research Preview。Dispatch 还支持 Computer Use，Claude 可以直接点击、滚动、操作你桌面上的应用。目前 Max 用户（$100/月）先用上了。

Chrome 扩展：给 AI 一双看得见的眼睛
-----------------------

Boris 说了一句很重要的话：

> "使用 Claude Code 最重要的技巧是：给 Claude 一种验证输出的方式。"

他的类比很到位：如果你让一个工程师做网站，但不让他用浏览器看效果，结果会好吗？大概率不行。给 Claude 一个浏览器，它就会写代码 → 看效果 → 发现问题 → 改代码 → 再看效果，直到满意。

之前我就是 Claude Code 的"人类脚手架"。它开发完成，启动本地测试服务器，然后我去浏览器查看效果，截图发回去，复制控制台的报错粘给它。现在 Chrome 扩展接上了，这些事 Claude 自己就能干。我从"脚手架"变成了"验收员"，只需要最后看一眼结果。

Chrome/Edge 扩展下载：https://code.claude.com/docs/en/chrome

桌面端内置浏览器预览
----------

和 Chrome 扩展类似的思路，但集成度更高。

Claude 桌面端可以自动启动你的 dev server，然后在内置浏览器里测试。它会自动截图、检查 DOM、点击元素、填表单，发现问题自己修。CLI 里需要手动配置，桌面端是开箱即用。如果你主要做 Web 开发，这个值得试。

官方文档：https://code.claude.com/docs/en/desktop#preview\-your-app

Fork 会话：一个分叉路口，两个方向都试
---------------------

经常遇到这种情况：和 Claude 聊了半小时，到了一个分叉路口，想试两个不同方向。以前只能复制粘贴开新会话，上下文全丢了。

现在两种方式：会话中运行 `/branch`，或者从 CLI 运行 `claude --resume <session-id> --fork-session`。

`/branch` 会在当前位置创建一个分支会话，两个会话共享之前的上下文，各自往不同方向走。比如你在做架构设计，Claude 提了两个方案，你想两个都试试——以前得开两个新会话重新描述需求，现在直接 fork。

功能看起来小，但在实际工作中省掉了大量重复沟通。

/btw：边干活边问问题，不打断主线
------------------

我觉得这可能是15条里最被低估的功能。

Claude 在执行一个长任务的过程中，你想问个快速问题怎么办？以前只能等它做完，或者打断它。`/btw` 是一个只读模式的快速问答通道——不触发工具、不修改文件，能看到当前对话的全部上下文，但不保存到主对话历史里。关闭后答案就消失了。

它还复用父会话的 Prompt 缓存，额外成本极低。

Boris 说他一直在用这个。想想也是：你让 Claude 做重构，跑了10分钟，突然想起来"对了，这个函数的返回类型是什么来着？"以前你得开个新终端查，现在直接 `/btw 这个函数返回什么类型？`，不污染主上下文，也不打断 Claude 的工作。

Git Worktrees：同时跑几十个 Claude，互不干扰
--------------------------------

Boris 说他同时跑着几十个 Claude 实例，靠的就是 git worktrees。

Worktree 是 git 的一个功能——简单说就是允许你在同一个仓库中创建多个独立的工作目录，每个目录可以 checkout 不同的分支，互不干扰。

用法：`claude -w` 在新的 worktree 中启动会话（会在 `.claude/worktrees/` 下创建独立目录和新分支）。也可以指定名称：`claude -w feature-auth`。2月19日发布，v2.1.49版本。

如果你在同一个仓库里同时跑5个 Claude 做不同任务，它们会互相踩文件。worktree 给每个 Claude 一个独立的沙箱，写坏了也不影响别人。

加上 `--tmux` 更方便：`claude -w feature-auth --tmux` 会自动创建一个 tmux session。

/batch：同时开上千个 agent 做代码迁移
-------------------------

这个听着就很猛。

`/batch` 的流程是这样的：它先问你想做什么（"访谈"阶段），然后启动一个编排 Agent 进入 Plan 模式。编排 Agent 会先发射 Explore Agent 调研影响范围，再把工作拆分成5-30个独立执行单元，每个单元在自己的 worktree 里并行跑。2月28日发布，v2.1.63版本。

![/batch 并行执行架构](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9znUD00niclialMh21XlGJPCHLewfmDOJUV3fvKGN0UDco3tibz6Ihc1oznYXOFiaZDv3HFXondoicePv2PzUOGJ16es3LRKFB8JOXA4/640?from=appmsg)

Boris 说这适合大规模代码迁移和其他可并行化的工作。

举个具体例子：你要把一个大型项目从 CommonJS 迁移到 ESM，涉及500个文件。以前只能一个个改，或者让 Claude 分批处理。现在 `/batch` 自动分析哪些文件可以并行改，然后同时开几十个 agent 各干各的。

我还没实际用过这个功能。但光想想——一个人指挥几十个 AI 同时改代码，产出相当于一个工程团队。

\--bare：脚本化场景启动速度提升10倍
----------------------

默认情况下，`claude -p` 启动时会搜索本地的 CLAUDE.md、settings、MCP 服务器、hooks、skills、plugins……一大堆东西。

但很多脚本化场景不需要这些。`--bare` 跳过所有自动发现，只保留 Bash、文件读取和编辑三个基础工具。3月20日发布，v2.1.81版本。

Boris 说启动速度最高提升10倍。这个数字取决于你装了多少 MCP、plugins、skills——装得越多，bare 跳过的东西越多，提速越明显。如果你本来就是裸配置，提升没那么夸张。但对写自动化脚本的人来说，哪怕每次省几百毫秒，大批量调用下来也很可观。

注意：bare 模式下 OAuth 和钥匙串读取也被跳过了，需要通过 `ANTHROPIC_API_KEY` 环境变量或 `--settings` 来认证。

用法：`claude --bare -p "你的查询"`

\--add-dir：跨仓库协作
----------------

跨多个仓库工作是常见场景。比如前端项目依赖一个内部 UI 库，两个是独立的 git 仓库。

`claude --add-dir ../ui-library` 不仅告诉 Claude 另一个仓库的存在，还给了它读写权限。Boris 说他通常在一个仓库启动 Claude，然后用 `--add-dir` 或会话中 `/add-dir` 加入其他仓库。2月17日起逐步完善，v2.1.45版本。

最新版本中，`--add-dir` 目录下的 CLAUDE.md 和 `.claude/skills/` 也会被自动加载。Claude 不仅能看到代码，还能理解那个仓库的规则和约定。

实际用途：你改了 UI 库的接口，Claude 能自动去前端项目里更新调用方式。

\--agent：自定义 Agent
------------------

Boris 说这是一个"经常被忽视的强大原语"。

做法：在 `.claude/agents/` 目录下定义一个 agent 文件，写好系统提示词和工具配置，然后 `claude --agent=<你的agent名称>` 启动。

你可以创建一个专门做代码审查的 agent、一个专门写文档的 agent、一个专门做安全扫描的 agent。每个 agent 有自己的性格和工具集。这和 skills 不同——skills 是指令集，agent 是一个完整的"角色"。你甚至可以给 agent 配不同的 MCP 服务器，让它有不同的能力。

官方文档：https://code.claude.com/docs/en/sub-agents

/voice：他说自己基本不打字了
-----------------

Boris 在帖子里写了一句让我意外的话：

> "Fun fact: I do most of my coding by speaking to Claude, rather than typing."

Claude Code 团队自己的人，写代码基本靠说话。

用法：终端里输入 `/voice`，然后按住空格键说话，松开后 Claude 处理你说的内容。桌面端点击语音按钮就行。支持20种语言，中文也可以。3月5日发布，v2.1.69版本。

![语音输入写代码](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9znonzXZ71dwtiaJpgOnHgFmTkYB3bibjvuoFxBEJUxELPlTsObvkIyLbrUTp118ibK0La2zEePhibYXJOZCt16Kz0LkLOWMAdkQiaEs/640?from=appmsg)

有个好玩的细节：你可以混合打字和语音。先打一半，按住空格说后一半，两种输入无缝拼接。不是全程监听，是按住说、松开发——这个设计很重要，不会把你开会的声音录进去。

手不方便的时候、口述需求比打字更快的时候、一边走路一边想事情的时候都能用。我还没正式用上，但知道了之后一直想试。

额外发现：Channels 频道系统
------------------

Boris 的帖子里没提这个，但我在调研过程中发现了。

你可以通过 Telegram、Discord、甚至 iMessage 给正在运行的 Claude Code 会话推送消息。不是开新会话，而是推到你已经打开的那个会话里。

比如你在终端里跑着一个 Claude Code 会话做重构，出门了。你可以在 Telegram 上给它发消息："顺便把那个 deprecated 的 API 也处理了"。消息直接到达正在跑的会话，Claude 继续干。

设置方式：安装 Telegram 插件 → 配置 bot token → `claude --channels plugin:telegram@claude-plugins-official` 启动。目前 Research Preview 阶段，需要 v2.1.80 以上版本。

官方文档：https://code.claude.com/docs/en/channels

* * *

发布时间线
-----

这些功能几乎全是2026年2-3月密集发布的，36个版本里塞进了这么多东西：

功能

版本

日期

\--add-dir 多仓库

v2.1.45

2月17日

Git Worktrees

v2.1.49

2月19日

Remote Control

v2.1.58

2月25日

/batch 扇出执行

v2.1.63

2月28日

/voice 语音输入

v2.1.69

3月5日

/loop + /schedule

v2.1.71

3月7日

/btw + /branch

v2.1.77

3月17日

Dispatch

—

3月17日

\--bare 加速启动

v2.1.81

3月20日

平均每3天一个重大功能。

* * *

这15条里我目前真正用上的是 worktree 和背景 Agent。`/loop` 和 `/schedule` 打算这周试，对重复性任务应该很有用。`/batch` 还没碰过，但想想一个人指挥几十个 AI 并行改代码的画面，确实有点期待。

回头看这些功能，有个感受挺强的：Claude Code 不再只是一个"你问它答"的终端工具了。手机能控制、定时能自动跑、上千个 agent 能同时干活——它越来越像一个真正的同事，而不是一个命令行窗口。

Boris 在最后说"我本来想继续写下去但不得不打住了，之后会分享更多"。等着了。

⭐以上，既然看到这里了，如果觉得不错，随手点个赞、在看、转发三连吧，谢谢你看我的文章，我们下次再见。

[今天你养虾了吗？](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485034&idx=1&sn=1334a42b733cd5d1334018f5e10b42be&scene=21#wechat_redirect)

[突发！Anthropic前研究员私下流出内部提示词手册，处处是细节](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484999&idx=1&sn=afde19bf4f65c49f00e6e71971655699&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言