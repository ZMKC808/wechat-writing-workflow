     如何让 Claude Code 在不知情时停止“胡编乱造” \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

如何让 Claude Code 在不知情时停止“胡编乱造”
=============================

原创 阿竹 AI飞升录 2026-06-08 10:38 浙江

> 原文地址: [https://mp.weixin.qq.com/s/97hOz4PZitdSozSfIqvP9Q](https://mp.weixin.qq.com/s/97hOz4PZitdSozSfIqvP9Q)

Claude Code 每天都在对你当面撒谎。编造的函数、虚构的导入、"测试通过"时其实什么都没跑。解决办法是一个四层机制，让撒谎的代价变得高昂。

Claude 告诉你 bug 修好了。两小时后你发现它调用的函数根本不存在。

大多数开发者学会了反复核查一切，然后去责怪模型。真正的解决办法是在每一个谎言离开你的机器之前就将其捕获。

**以下是完整的诚实机制** 👇

![rody - inline image](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9znqznC451DZGZVyQTNYGAgpNjQ09gY02Gk8RRP24JuobGTsaqqs1OINSTbuBX7qp7xP0kmjQx9eibXZg7zwB8JotkKs0b02AYbM/640?wx_fmt=jpeg&from=appmsg)

**为什么 Claude 会瞎编**
------------------

Claude 本质上是一个文本预测器。当它不知道某件事时，它会预测那些看起来合理的文本。编造的函数名看起来像真的。信心满满地说的胡话，和信心满满地说出的真相，读起来没有区别。

只有等到两小时后你的代码崩溃，并且你还得多花一小时调试时，你才看得出区别。

解决办法不是更聪明的模型。而是让 Claude 的输出能够实时被检查，并且让"我不知道"的成本低于瞎猜。

下面这 4 层机制，加在一起几乎能把瞎编的概率降到零。

![rody - inline image](https://mmbiz.qpic.cn/sz_mmbiz_jpg/JYWVQlsu9zn6KoUPsfcuibLXvM6ZxDTkVibcIW17IXpJvYEibudZytlfEreyKFAq1DqPVKZxLMVzibLL42Wp9jCGcmTlRRicuapSTyNjy5mAUNmg/640?wx_fmt=jpeg&from=appmsg)

**CLAUDE.md 中的诚实规则**
--------------------

第一层是在 CLAUDE.md 中设置一组规则，明确告诉 Claude 在什么时候、以什么方式承认不确定性。把这个放在你的项目根目录：

    ## 诚实规则（每次对话回合都要阅读）在声称某个函数、类或导入存在之前，请先通过读取文件或运行 grep进行验证。切勿捏造符号名称。如果无法验证，请明确说出"我还没验证这一点"。不要编写依赖未经验证的声明的代码。如果任务要求你使用在这个项目中从未见过的库，请先询问再添加。如果任务涉及测试或构建，除非你真的在此会话中运行了测试或构建命令，否则不要声称成功。切勿编造错误信息、API 响应或堆栈跟踪。如果你没亲眼看到，就如实说。当你真的不知道时，正确的答案应该是"我不知道"或"我需要先查一下"。这两种回答都比自信的猜测要好。

这些规则看起来显而易见。

但实际上并非如此，因为 Claude 默认是被优化成显得"乐于助人"的，而"我不知道"除非你明确许可，否则会显得不够有用。

最后一行是最重要的。它是说"我不知道"的许可，而大多数人从未给予这个许可。

**先验证再写入的模式**
-------------

第二层强制要求 Claude 在写入之前先进行验证。把这段内容加到 CLAUDE.md 中的诚实规则下面：

    ## 验证协议在编写或编辑使用某个符号（函数、类、类型、常量）的代码之前，请执行以下操作之一：1. 读取定义该符号的文件，确认签名2. 运行 `grep -r "符号名" .` 或使用 Glob 工具找到它3. 检查 package.json、requirements.txt、Cargo.toml 或类似的依赖清单如果跳过验证，请在代码前加上注释：`// UNVERIFIED: 我尚未确认此符号是否存在`对于涉及多个文件的任务，优先使用"先计划后执行"模式。在开始之前使用 Shift+Tab 进入计划模式。

这会让 Claude 每次会话多花几次工具调用。但换来的是节省了你本可能要花在调试虚构函数调用上的数小时时间。

**实时捕获谎言的钩子**
-------------

第三层是在 **settings.json** 中设置钩子，每当 Claude 写入一个文件时就运行类型检查器或 linter。如果 Claude 凭空发明了一个导入，检查器会立即失败，Claude 必须在声称任务完成前修复它。

    {"hooks": {"PostToolUse": [      {"matcher": "Write(*.ts|*.tsx)|Edit(*.ts|*.tsx)","hooks": [          { "type": "command", "command": "npx tsc --noEmit --pretty false 2>&1 | head -20" }        ]      },      {"matcher": "Write(*.py)|Edit(*.py)","hooks": [          { "type": "command", "command": "ruff check --quiet $file && pyright $file 2>&1 | head -20" }        ]      },      {"matcher": "Write(*.rs)|Edit(*.rs)","hooks": [          { "type": "command", "command": "cargo check --message-format=short 2>&1 | head -20" }        ]      }    ]  }}

钩子的输出会作为上下文返回给 Claude。如果 tsc 说"找不到模块 'foo'"，Claude 会立即看到并修复这个编造的导入。没有凭空编造的代码能逃过 **PostToolUse** 检查。

对于涉及测试的任务，添加一个 **Stop** 钩子，在 Claude 宣称会话完成之前运行测试套件：

    "Stop": [  {"hooks": [      { "type": "command", "command": "npm test 2>&1 | tail -30" }    ]  }]

现在 Claude 不能再在没有实际运行测试的情况下说"完成了，测试通过"。钩子会执行它们。

结果会返回给 Claude。如果测试失败，Claude 必须修复它们或者承认测试没有通过。

**事实核查子 Agent**
---------------

第四层是一个子 Agent，它的唯一工作是在 Claude 的声明"发布"之前对其进行核查。

把这个放在 **.claude/agents/fact-checker.md**：

    ---name:fact-checkerdescription:在Claude对代码功能、测试结果或库支持情况做出声明后使用此Agent。在每次提交前、每次面向用户的总结前，以及任何引入新依赖的任务后调用。tools:Read,Grep,Glob,Bashmodel:sonnet---你负责验证声明，不编写代码。被调用时，请执行以下操作：1.识别最近对话中的每一个事实性声明。例如："函数 X 执行 Y 操作"、"测试通过了"、"库Z支持W功能"、"这个导入是正确的"。2.对每个声明进行独立验证：-代码声明：读取实际文件并确认-测试声明：亲自运行测试-库声明：检查实际的包或其文档-导入声明：确认包在依赖清单中3.生成一份报告：-VERIFIED:声明、证据（文件:行号或命令输出）-WRONG:声明、实际情况是什么-UNVERIFIABLE:声明、无法检查的原因永远不接受"相信我"之类的声明。永远不要做出你自己的声明。如果你无法验证，正确的输出是UNVERIFIABLE。

在提交之前或与团队分享结果之前调用此 Agent。它能捕获其他 3 层遗漏的谎言。

![rody - inline image](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zkv1S3UdSib68e1OIR0VQJvjrc4PmXjS9cXsdAZz5j9E06ooOX9dlo8UQfWECQNHTOL0zLWXuxkpVsBxAxBmu6u7l1AZlXhuy58/640?wx_fmt=png&from=appmsg)

**"我不知道"的许可**
-------------

Claude 被训练成要乐于助人，而承认无知感觉上不太乐于助人。所以它猜测，并且猜测看起来和真相一样合理。

解决办法是给予不知道的许可。CLAUDE.md 是其中一半。你的反应是另一半。用耐心来奖励"我还没验证这一点"，你每次会话都能得到一个诚实的 Claude。用不耐烦来惩罚它，Claude 就会回到瞎猜的状态。

这不是一个配置，而是一种习惯。是整个方案中最被低估的解决方案。

**如何判断它真的在起作用**
---------------

留意你日常会话中的三个迹象。

Claude 在添加依赖之前会询问。"我应该添加 X 还是使用标准库？"而不是默默地 **npm install。**

Claude 在谈及现有代码时会引用文件:行号。"**src/auth/middleware.ts:47 的 validateToken** 执行 Y 操作"而不是"validateToken 函数执行 Y 操作"。

tsc 和你的 linter 不再报错。钩子能立即捕获极少出现的捏造，Claude 会自我修正。所以等你去看的时候，谎言已经消失了。

一两天后还没看到这些现象？说明某个层没加载成功。通常是 CLAUDE.md，位置不对或者名字不对。

![rody - inline image](https://mmbiz.qpic.cn/sz_mmbiz_jpg/JYWVQlsu9znvanBV0sj5B3m2UcphQLQtCBN2AG9A4RZKZwrIxSvUQCGUp6Au1nUm8mvbMsuDYg5hKInATvjPGWV9s5cD35C41x8RgcGzPCs/640?wx_fmt=jpeg&from=appmsg)

**让 Claude 持续撒谎的常见错误**
----------------------

**CLAUDE.md 太长。** Claude 只读前半部分，后面的就扫一眼。诚实规则要放在前 50 行。

**钩子静默记录。** 如果输出没有到达 stdout，Claude 就不知道它撒谎了。确保钩子的输出能返回到会话中。

**你跳过了计划模式。** 那是 Claude 在动手写之前暴露错误假设的地方。跳过它，就等于错过了捕获谎言最便宜的时机。

**你不调用事实核查器。** 子 Agent 只有在你真正调用它时才起作用。把 @fact-checker 纳入你的提交流程。

**你对"我不知道"反应不佳。** 惩罚诚实一次，Claude 就会回去瞎猜。没有这个习惯，其他 3 层也坚持不下去。

![rody - inline image](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmnlWGMB7MeRyPnQdx6VKfH4JNZNYzZN2RrJQJAQEGRRCFDyx87YPqsm5GMicxnhvic3J7BnTI71QRUdicTic3sXkP0gEe7iaSEWbvg/640?wx_fmt=png&from=appmsg)

**5 分钟诚实审计**
------------

1 分钟：将 CLAUDE.md 的诚实规则和验证协议复制到你的项目根目录。

1 分钟：将钩子块复制到 **~/.claude/settings.json** 或 **.claude/settings.json**。

2 分钟：使用上面的模板创建 **.claude/agents/fact-checker.md**。

1 分钟：运行一个你通常会反复核查的任务。留意 tsc 的输出是否返回给 Claude。确认 Claude 明确说出"已验证"或"我还没验证这一点"。

完成。捏造从"每次会话都发生"降到"很少出现且立即被捕获"。模型没变聪明。是你的设置变聪明了。

⭐如果你希望下次也能接受到此等质量的好文 请务必将我们星标，防止迷路！转给你的亲友一起变强！

[6月底截止｜无限 Token，Claude Code 爽用 Qwen3.6](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485828&idx=1&sn=37a41f3b84451f4bf7d9eb7c34febd15&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言