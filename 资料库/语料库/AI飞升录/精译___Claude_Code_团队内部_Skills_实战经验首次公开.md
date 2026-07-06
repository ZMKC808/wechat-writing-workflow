     精译 | Claude Code 团队内部 Skills 实战经验首次公开 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

精译 | Claude Code 团队内部 Skills 实战经验首次公开
=====================================

原创 阿竹 AI飞升录 2026-03-25 12:53

> 原文地址: [https://mp.weixin.qq.com/s/oVyJ6KAOwk\_bk4dRG1parw](https://mp.weixin.qq.com/s/oVyJ6KAOwk_bk4dRG1parw)

我之前以为自己会用 Skills。
=================

写一个 SKILL.md，告诉 Claude 怎么干活，格式规范、输出要求、注意事项，洋洋洒洒三四百字。用了几次，感觉还行。

直到看完 Anthropic 工程师 Thariq Shihipar 这篇内部复盘，才意识到自己压根没用对地方。

你写进去的，Claude 早就知道了
------------------

Thariq 的文章里有句话含金量很高：

> Claude Code 已经非常了解代码库，Claude 本身也很懂编程，有大量默认观点。如果你发布的 Skill 主要是在提供知识，就专注于那些能让 Claude 脱离正常思维方式的信息。

大多数人写 Skill，把 API 用法格式化了一遍，把官方文档精简了一下，花了半小时，Claude 看完微微点头，然后什么都没变。因为它早就在预训练数据里见过这些了。

真正让 Skill 有价值的信息，有一个特征：查遍全网找不到。因为它根本不在网上。

高语境知识：只有你自己踩过才知道的东西
-------------------

有本书叫《超越文化》，作者 Edward T. Hall 提出了一个框架：低语境沟通依赖字面信息，高语境沟通依赖共享背景和默认规则。

你跟合作了三年的同事说"老规矩处理一下"，他立刻知道该怎么做。同样的话跟刚来的实习生说，他一脸懵。

你现在调教的 Skill，就是那个实习生。

Claude 把低语境信息全吸收了。API 文档、技术规范、操作步骤，它比你记得还清楚。但一旦进入真实工作流，卡住它的是高语境信息：你们内部那个审批流程文档里标着"可选"，但实际上不走这一步后面全卡死；那个库的 init 方法看起来没问题，但到线上环境会在某个边界情况炸掉；那张监控面板的数据"准"，但要跟另一张表 JOIN 才是组织内认可的真实口径。

这些信息只存在于踩过坑的人脑子里。

Thariq 说，一个 Skill 里**含金量最高的部分是坑点总结（Gotchas）。**每次踩到新坑，就更新进去。好的 Skill 随着使用把失败经验一条条沉淀进去，越用越强。

* * *

Anthropic 内部跑着数百个 Skills，归成了这 9 类
---------------------------------

Thariq 把内部所有 Skills 梳理了一遍，发现自然聚成 9 个类别。对照这份清单检查一次，大概率你的团队只用了第一类。

![Anthropic 内部 Skills 9 类分类](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9zlOwnTmFPF0hMh8t3pq9AbwcwCgBCbgMBCibXBOPdmm8yxr14qsYfRT1efqzJ92IibeclAPRASvR8jXDduicwhbcNHqpXQUrLSl8M/640?wx_fmt=jpeg&from=appmsg)

### 1\. 库与 API 参考

帮 Claude 正确使用某个代码库或 SDK。重点放在那些"模型默认会用错"的部分，把你们内部踩过的边界情况写进去，而不是复制官方文档。

### 2\. 产品验证

告诉 Claude 怎么验证代码真的跑对了，通常配合 Playwright、tmux 这类工具。Thariq 说了一句让我印象很深的话：值得让一个工程师花整整一周，专门把验证 Skill 打磨好。生成能力决定 AI 能做多少事，验证能力才决定你敢让它做多少事，差距在这。

### 3\. 数据获取与分析

给数据路径，而不只是给数据。"看注册到付费的漏斗需要 JOIN 哪几张表"，"这个报错该先看哪个 Dashboard"——这种路径原本只存在于数据负责人脑子里，可以沉淀进 Skill。

### 4\. 业务流程自动化

把团队里重复出现的工作流收敛成一条命令。日报整理、工单创建、周报生成。一个关键细节：把历史执行结果存成日志，模型下次做同类任务时会更稳，口径不会漂移。

### 5\. 代码脚手架

生成符合你们规范的框架代码，提前把认证、日志、部署接好。Claude 在里面边生成边判断，适合那些"有自然语言要求、代码生成覆盖不了"的脚手架场景。

### 6\. 代码质量与审查

强制执行你们团队的代码规范。可以启动一个专门的"挑刺"子 Agent 来批评代码，实施修复，循环迭代到找不出大问题——把团队对"什么叫好代码"的标准变成可以反复跑的流程。

### 7\. CI/CD 与部署

监控 PR、重试不稳定的 CI、灰度发布、出现退化自动回滚。这条链路出错代价不小，这类 Skill 帮团队把一条高风险流程做稳。

### 8\. 运行手册

输入一条告警或一段报错，走完多工具排查，输出结构化的排查报告。把资深工程师的排查路径变成团队资产，下一个人不用从头摸。

### 9\. 基础设施运维

查孤儿资源、调查成本异常、依赖审批。这类 Skill 里有些操作具有破坏性，需要内置防护栏，让工程师在执行关键操作时有明确的最佳实践可循，而不是全靠经验和胆量。

让 Skill 从能用变成越用越强的 5 件事
-----------------------

![Anthropic 9 个最佳实践总结](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9zl7B0082ericCjiaWLXVaCiaRIYPWa8oB9nIMa3m1mKzibV2fBuQ1sJuWXvvH4nicCHtJp38dLNiafmS66sFicF6bFJIIiaEQaFZo2Qbkg/640?wx_fmt=jpeg&from=appmsg)

### Description 是触发条件

Claude Code 启动时扫描所有 Skill 的 Description 字段，决定什么请求用哪个 Skill。这个字段是写给模型的触发条件，该在什么场景下激活、什么场景下不出现，都要想清楚写进去。

写"这是一个翻译工具"，用户说"把这篇论文出个中文版"时可能就匹配不上了。好的 Description 精准得像一个 if 条件，这个细节直接决定 Skill 在该出现的时候能不能出现。

![Description 好坏对比：太宽泛的描述 vs 精准的触发条件](https://mmbiz.qpic.cn/sz_mmbiz_jpg/JYWVQlsu9znqjOtLoIFzdxKLjKNpkJHvxjxNHq8PDALfhaN8yQmjAunDUL8uTHPh4QPtLN8ttw7iaje3IOawvLibWruJn2PUK7DgldecVDr7Y/640?wx_fmt=jpeg&from=appmsg)

### 给 Skill 配上记忆

Skill 可以把数据存在自己目录里——追加日志、JSON 文件，甚至 SQLite 数据库都行。

`standup-post` 这个 Skill 保留了每天的日报历史，第二天运行时先读记录，知道今天和昨天相比真正新增了什么，只汇报变化的部分，这才是有用的日报。没有记忆，它每次都从零开始，每次都像第一次见你。

![standup-post/SKILL.md 的 Memory 配置：每次执行后把内容追加进日志](https://mmbiz.qpic.cn/sz_mmbiz_jpg/JYWVQlsu9zkrTUHynCtINhUPzfj8N1obDRsY05Xy4MLXFIicxRIF1nUpBoia6vK13FEDZhmIYMyLDmILQlWUl0wdmSSibo6ibiaGPTfribQuEgHQI/640?wx_fmt=jpeg&from=appmsg)

### 把脚本放进去

把常用脚本和 helper 函数放进 `scripts/` 目录，Claude 就能把全部精力花在组合和判断上，而不是每次重建取数逻辑或者模板代码。

一个数据分析 Skill 预置好了取数函数，你问"上周二发生了什么"，它直接调函数生成分析脚本，而不是先卡在"数据怎么取"这一步。这个差距，真用了才知道有多大。

### Skill 是文件夹，用文件结构做渐进式展开

详细 API 文档放 `references/api.md，`模板文件放 `assets/，`脚本放 `scripts/，`告诉 Claude 里面有什么文件、分别干什么用。它会在需要的时候自己去读，信息分层，按需展开，而不是把所有内容一次性塞进上下文。

### 按需 Hook

`/careful` 激活后会拦截 `rm -rf、``DROP TABLE、``force-push，`专门用于操作生产环境的场景。`/freeze` 开启后 AI 只能编辑指定目录，调试时防止它顺手改了不该动的地方。这些 Hook 只在 Skill 被调用时生效，会话结束自动关闭。一直常开会烦死人，但关键时刻不开是真的出事。

经验第一次有了可以复利的载体
--------------

想象一下过去的情况：一个高级工程师花了两周搞清楚内部计费库的所有陷阱，这些知识存在哪里？存在他脑子里，或者一个没人维护的文档页面。下一个接手的人大概率要重新踩一遍。

现在，他把这些经验写进 `billing-lib` Skill，推进团队内部市场。之后每个工程师都自动获得了他两周积累的经验，每次踩到新坑还会继续更新进去。

Anthropic 内部的运作方式：没有中央团队来审批，让 Skill 自然生长。觉得好用，先放 GitHub 沙盒，在 Slack 里告诉同事，有人用了口碑传开，再提 PR 进 Marketplace。他们还用 `PreToolUse` Hook 做了使用统计，能看到哪些 Skill 被调用最多、哪些触发率低于预期，Skill 的好坏有数据可查。

一个有 200 个高质量 Skills 的团队，和一个只有 10 个的团队，AI 协作效率的差距大概率在 10 倍以上。这种差距是复利式增长的，而且外人看不见——只能看到"这个团队的 AI 用得特别好"，看不到背后跑着多少隐形基础设施。

Thariq 在结尾说了一句很诚实的话：我们内部大多数 Skill 最开始只有一行说明加一个坑点，随着大家不断撞上新的边界情况，修修补补，才变得越来越好用。

从最痛的那个任务开始。先列出你踩过的几个最大的坑，写进 Gotchas，把触发条件写清楚，加上能直接复用的脚本。先做出一个真的能帮你减少返工的 Skill，比做出一个看起来完整、实际没人用的更有价值。

* * *

⭐以上，既然看到这里了，如果觉得不错，随手点个赞、在看、转发三连吧，谢谢你看我的文章，我们下次再见。

[全网首发，Anthropic 发布官方「龙虾」](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484947&idx=1&sn=8fa9d6abacf25f052f9952621bbcb6bd&scene=21#wechat_redirect)

[刚刚，微信可以接入"龙虾"了，10分钟教你搞定](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484937&idx=1&sn=e267b0c8b885ae5fa8094002d5d56464&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言