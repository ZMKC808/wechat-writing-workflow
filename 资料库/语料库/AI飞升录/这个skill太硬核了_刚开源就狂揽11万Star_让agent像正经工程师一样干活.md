     这个skill太硬核了！刚开源就狂揽11万Star！让agent像正经工程师一样干活 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

这个skill太硬核了！刚开源就狂揽11万Star！让agent像正经工程师一样干活
==========================================

原创 阿竹 AI飞升录 2026-03-27 18:00 浙江

> 原文地址: [https://mp.weixin.qq.com/s/ptZmpiWYySHtfWUxDbC0EQ](https://mp.weixin.qq.com/s/ptZmpiWYySHtfWUxDbC0EQ)

上周我用Claude Code写了个数据处理脚本，两个小时交付。
================================

打开一看：函数套函数，变量名`temp1、``data2，`同一段逻辑复制粘贴了三次，测试零个。能跑，但我不敢动它。

后来花了比写代码多一倍的时间在理它。

这个体验挺有代表性的。AI写代码快，快在"立刻开始写"——它猜你的意图，绕过设计，跳过测试，给你一堆功能上没问题、工程上一塌糊涂的代码。速度快换来的是后期维护成本高。

直到我看到GitHub上这个项目——**Superpowers，**11万Star，作者Jesse Vincent，专门解决这个问题。

![Superpowers核心理念与流程说明](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9znW8uE9wNOrWJNdYDwwbZewhfL2ia5KYKcqVoZhibWg2LicNPOlYlmvRmnyg1jyWcDOCwwJPxaJQaraIY0ZRbMz9hfgQl13gfsYN8/640?wx_fmt=png&from=appmsg)

AI猜你想要什么，这件事本身就是问题
------------------

我以前用AI写代码的方式：丢需求，等输出。

这是Push模式——我推，AI接。AI拿到不完整的信息，用猜来补全，猜对了OK，猜错了就是一堆需要返工的代码。

有个效率更高的交互方式：把目标和背景丢出去，让AI反过来问你。它一个问题一个问题地把你脑子里的模糊需求拉出来，需求清楚了再给方案。这叫Pull模式。

Superpowers做的事是把Pull模式固化进agent的默认行为——装上之后，agent在写代码之前会先停下来问你问题，主动澄清需求、边界和设计方案，达成共识了才开始执行。

7步完整流程，每一步都有具体约束
----------------

Superpowers包含17个可组合的skill，覆盖从需求讨论到最终合并的完整链条。不是一段提示词，是一套有执行约束的工作流。

**Step 1：头脑风暴，先聊清楚再动手**

你说想做什么，agent会退一步，问你：实际要解决什么问题？有什么限制条件？设计上有几个备选方向？整理成规格说明，分块给你确认。双方对"做什么"有共识，才进入下一步。

**Step 2：隔离工作环境**

设计确认后，agent用Git Worktree创建独立开发分支，和主代码库彻底隔开。跑一遍测试确认基线干净，再开始。

**Step 3：把计划拆到极细**

这步是整套流程的核心。agent把设计拆成一个个2到5分钟能完成的小任务，每个任务里有精确的文件路径、完整的代码示例和验证步骤。

项目原文里对这个粒度有个描述我觉得很到位：

> 详细到"一个热情洋溢但品味堪忧、缺乏判断力的初级工程师也能照着执行"。

任务粒度越细，执行偏差越小。

![任务拆分与子Agent并行执行](https://mmbiz.qpic.cn/sz_mmbiz_png/8uA0NGWE8FmtQnC83yY27UNia0kLvhlDcNSd4Nn0USCXPajrKJ7bvwr7mMWbM2IUTzSD3R5r6P6OcNo2wgJUHNsUwLeCVic6ScIS8y4aAdJdg/640?wx_fmt=png&from=appmsg)

**Step 4：子agent并行执行，双轮审查**

每个小任务派出一个全新的子agent处理，任务之间互相隔离。每个子agent完成后过两轮审查：第一轮查规格符合度，第二轮查代码质量。整个过程可以自主跑数小时，不会偏离计划。

**Step 5：强制TDD，测试前写的代码直接删**

Superpowers的最硬核部分。强制执行RED-GREEN-REFACTOR循环：先写失败的测试，确认它真的失败，再写最少量的代码让它通过，通过后才提交。

检测到有代码是在对应测试之前写的——系统直接把它删掉。

没有测试的代码在Superpowers里视为不存在。

**Step 6：代码审查按严重程度分级**

每个任务完成后自动触发审查，输出按Critical/High/Medium/Low分级的问题报告。Critical级别的问题直接阻断流程，不处理不允许继续。

**Step 7：收尾确认，清理环境**

全部任务跑完，验证测试全部通过，给你四个选项：合并到主分支、创建PR等待Review、保留分支继续、或直接丢弃。最后清理工作环境。

这段提示词可以直接用
----------

暂时不想装整套工具的话，可以把下面这段提示词丢给AI，手动触发Pull模式：

`请你在回答前，先问我问题。要求：   1. 一次只问我一个问题。   2. 根据我的回答继续追问，不要并行甩出一堆问题。   3. 先帮我澄清目标、场景、限制条件、成功标准和边界。   4. 直到你有95%的把握理解我的真实需求，再给我方案。   5. 如果你发现我的需求本身有问题，直接指出，并继续追问。   `

我用了一段时间，体感是：AI问完问题再给的方案，要改的次数少了很多。根本原因是它拿到了足够的信息，猜测成分少了。

支持的工具
-----

Claude Code（官方插件市场一键安装）、Cursor（插件市场搜索安装）、Codex、OpenCode、Gemini CLI。

开源，MIT协议，GitHub地址：https://github.com/obra/superpowers

![Superpowers GitHub项目页](https://mmbiz.qpic.cn/sz_mmbiz_png/8uA0NGWE8FkEHr8WNxzllibIkjdqz1QiaLavoCoYBJrxhZYnFmqgYpoq1cicvM8ZvsTECRia9B7InO8Vt3qAVxSypP1lWena2CkF4wUGaAvIkIY/640?wx_fmt=png&from=appmsg)

它解决的是哪个层面的问题
------------

Superpowers的底层思路：系统化执行优于临时发挥，用测试证明代码可用，任务粒度降到最小，完成标准在开始前就定好。

之前的问题不是AI写不好代码，是我们只给了它工具，没给它做工程的方法。一个刚入职的工程师拿到电脑就让他开干，结果差也是正常的。Superpowers做的是把方法论这层补上去。

⭐以上，既然看到这里了，如果觉得不错，随手点个赞、在看、转发三连吧，谢谢你看我的文章，我们下次再见。

[限时白嫖谷歌Gemini pro会员 | 无需Pixel设备，亲测有效！](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484969&idx=1&sn=8a658a3c3590e0b6e9a69a9dbf3808bb&scene=21#wechat_redirect)

[精译 | Claude Code 团队内部 Skills 实战经验首次公开](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484956&idx=1&sn=5e3aad595c239b6efd3a2f45355139fd&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言