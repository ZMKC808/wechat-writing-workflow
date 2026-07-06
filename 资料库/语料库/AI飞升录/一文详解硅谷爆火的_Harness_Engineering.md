     一文详解硅谷爆火的 Harness Engineering \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

一文详解硅谷爆火的 Harness Engineering
=============================

原创 阿竹 AI飞升录 2026-03-28 12:45 浙江

> 原文地址: [https://mp.weixin.qq.com/s/kGmmca2yWokw0QWlgT7NHA](https://mp.weixin.qq.com/s/kGmmca2yWokw0QWlgT7NHA)

2026年最火的技术概念，最近终于有人讲清楚了。
========================

同一个AI模型，什么都不换，只改了一套"框架"，编程成功率从42%飙到78%。硅谷工程师圈子这段时间都在聊一件事：Harness Engineering。

OpenAI发了内部实验报告，ThoughtWorks首席科学家Martin Fowler说它是AI编程的关键，HashiCorp联合创始人Mitchell Hashimoto说他做了好几年，只是以前没有统一的名字。

看了各种解释还是有点晕？这篇文章用大白话把它讲透。

![](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zk0HDeJwBf7Eibx4ic8LJMUicTrfSEBKHnsfD5ktBmspt7NoRIT7SAOwvAGtEerxClSxW9CLQmLlQMFCUboqPMQ5WhPagnV8kGxT8/640?wx_fmt=png&from=appmsg)

Harness是什么
----------

Harness这个词，英文原意是马具，缰绳、马鞍、围栏和道路，套在马身上让它能被引导的那整套东西。没有它，再强壮的马也只是一匹乱跑的野马。

对应到AI：**模型是马，Harness是让它跑得有方向、有节制、不出轨道的那整套系统。**

公式很简单：**Agent = Model + Harness**

如果你不是模型，你写的、配的、搭的所有东西，都属于Harness。

Harness里有什么：系统提示词定义角色和规则，工具和MCP接口是模型能调用的外部能力，文件系统和运行环境是Agent干活的地方，编排逻辑负责子Agent调度和任务拆分，钩子和中间件在关键节点做自动检查，还有上下文压缩和记忆管理。

模型本身是纯函数，输入文本，输出文本。它不记忆、不执行、不联网、不自我纠错，这些能力全部靠Harness来补。

![Harness架构图：Context Injection、Control、Action、Persist、Observe五个方向围绕Model](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9zl8qmtrs88yF8jr2syWFazmgDjajUu6iaia98YSpp1ibqgQNmUicCZLSaZ8oS4NQNicZ0DoeJlwLgSMAVRfKZ5pIEnZ3RO5NlA0CHCw/640?wx_fmt=jpeg&from=appmsg)

AI工程的三次范式迁移
-----------

理解Harness，要从AI工程的演进路线看。

**第一阶段（2022-2024）：Prompt Engineering**

核心问题是"怎么问"。告诉模型一步步想，给例子，结构化输出。瓶颈很快出现：提示词写得再精准，模型缺关键上下文，该错还是错。

**第二阶段（2024-2025）：Context Engineering**

核心问题变成"给什么"。上下文窗口是有限资源，而且存在 Context Rot 这个现象，上下文越长，有效信息比例下降，关键线索被淹没，推理能力开始飘。技术重心转向压缩、动态检索、按需加载，重点是塞对的，而不是塞更多。

**第三阶段（2026至今）：Harness Engineering**

核心问题变成"构建什么环境"。单靠更好的提示和上下文管理还不够，模型需要一套工具、约束、反馈循环和记忆机制的完整配套。Context Engineering是Harness的一部分，Harness还多管了架构约束、自动审查和质量检查。

三层关系：**Prompt管你问什么，Context管你给模型看什么，Harness管整个系统怎么运转。**

两个让人服气的案例
---------

### OpenAI：3个工程师，5个月，100万行代码

2025年8月，OpenAI Codex团队立了个规矩，仓库里每一行代码必须由Agent写，人不能直接写代码。

五个月后：100万行代码，约1500个PR合并，人均每天3.5个PR，吞吐量随团队扩大还在增加，因为更好的Harness产生了复合效应。

他们具体做了什么？

设计了一个初始化Agent，专门在开发开始前搭脚手架：创建 `init.sh` 脚本（每次会话用同一条命令启动环境，不浪费Token去摸索）、维护一个JSON格式的功能列表（200多个端到端功能，每个标记是否通过，不让Agent靠猜来判断任务是否完成）、维护 `claude-progress.txt` 进度文件（每次会话结束前更新，下一个Agent实例直接读这份进度，不用从头考古）。

编码Agent和初始化Agent分开，初始化Agent只搭环境，编码Agent每次只做一个功能，完成后git提交并更新进度文件，保持干净交接。

架构约束用自定义Linter机械化执行，不靠人工代码审查。Agent生成违规代码时，错误消息里直接包含修复指令。

![OpenAI Codex团队Harness Engineering实验报告配图](https://mmbiz.qpic.cn/sz_mmbiz_png/aNEfzwzDSW9UrC8uKkWYxnibuZPXngfpBGGrbXw4339adTVaiaic7gCQJ30lCriaDo9um197QsuKDJjmJxJTAp6QX5lUBlZ1KsdLrPpaUdJtNdY/640?wx_fmt=png&from=appmsg)

### Anthropic：让AI评AI，不让AI自己给自己打分

Anthropic搭了一个三Agent架构，灵感来自生成对抗网络。

规划者把"帮我做一个浏览器端音频工作站"这句话，拆成16个功能、10个开发阶段的完整规格说明。生成者每次只做一个功能，不贪多。评估者用Playwright实际操作应用，点按钮、填表单、测边界情况，打分、提Bug。

4个小时，124美元，跑出来一个完整的浏览器端数字音频工作站。

让AI自己评价自己的作品，十有八九说"我觉得挺好"，哪怕在人看来稀烂。把执行和评估分开，这个问题就解决了。

![](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmNMCs0IbZayPicZNVzc1TsjhKTWgeZSiaCAAalg9icvpnkia12UWX5x37CPKPtstNyd4eGibdiaLAEXBFcJZAE9XCj7DvToYCxWOR9Q/640?wx_fmt=png&from=appmsg)

Harness最反直觉的地方
--------------

上下文越多，Agent越聪明——这个直觉是错的。

普林斯顿NLP团队的SWE-agent论文记录了一个Agent最常见的死法：发出一个grep命令，返回几千行匹配，然后迷失在这堆噪音里，接着发更多grep，上下文越来越乱，最后产出错误答案或者直接卡死。

他们的修复方案极其简单：搜索结果超过50条就截断，告诉Agent"结果太多，请缩小范围"。论文消融实验里，这一改动的杠杆率最高。

**上下文是稀缺资源，噪音和有效信息争夺的是同一批注意力预算。** 好的Harness主动保护Agent不被自己淹死，不是给它更多，而是只给它需要的那些。

怎么搭你自己的Harness
--------------

Mitchell Hashimoto（Terraform创造者）给了一个极朴素的方法：**每次Agent犯错，就工程化一个方案，让它再也犯不了同样的错。**

他给自己终端模拟器Ghostty的配置文件里，每一行规则都对应着Agent过去犯过的一个错。文件是活的，一直在长。

**给地图，不给说明书。** CLAUDE.md或AGENTS.md应该像地图：项目结构、文件关系、关键约束、什么地方不能碰。不要把每步都写死，Agent需要方向感，不需要僵化步骤。

**每次犯错加一条规则。** 从空文件开始，Agent犯一个错就加一条。三个月后那个文件就是你的Harness，高度定制，因为全是你自己场景里真实出过的问题。

**让AI查AI。** 不要让同一个Agent自查自纠。写完后开一个新对话，把结果贴进去"找出所有问题"。第二个AI能发现的漏洞会让你惊讶。

我自己的CLAUDE.md就是这么长出来的。被AI搞烦了就加一条，规则太多了就砍一轮，活的系统。

Harness的本质，是把你脑子里"什么叫做好"的标准写出来，变成Agent可以感知和遵守的约束。模型越来越强，但你脑子里的标准它永远看不见，除非你把它写进Harness。

⭐以上，既然看到这里了，如果觉得不错，随手点个赞、在看、转发三连吧，谢谢你看我的文章，我们下次再见。

[这个skill太硬核了！刚开源就狂揽11万Star！让agent像正经工程师一样干活](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484974&idx=1&sn=321f1f83eb298f6351d8fdc75fea3dce&scene=21#wechat_redirect)

[限时白嫖谷歌Gemini pro会员 | 无需Pixel设备，亲测有效！](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484969&idx=1&sn=8a658a3c3590e0b6e9a69a9dbf3808bb&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言