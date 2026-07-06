     GLM 5.2实测：把Claude、GPT、Kimi全拉进来比了一遍，这次真超Opus了？ \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

GLM 5.2实测：把Claude、GPT、Kimi全拉进来比了一遍，这次真超Opus了？
=============================================

原创 阿竹 AI飞升录 2026-06-15 15:18 浙江

> 原文地址: [https://mp.weixin.qq.com/s/GyFDwdpCNZoHvJgbO0uVng](https://mp.weixin.qq.com/s/GyFDwdpCNZoHvJgbO0uVng)

上篇发过，[GLM-5.2模型上线，实测给力](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485960&idx=1&sn=42c57bd3b0133c79eac73b83b0149e9e&scene=21#wechat_redirect)

新模型上线后，到处都在说追平Opus 。到底是不是真的？今天就给大家做一期评测，把Claude、GPT、Kimi、MiniMax全拉进来，同一个项目跑一遍，用数据说话。

GLM-5.2基于GLM-5.1迭代，总参数 **744B** 、活跃参数 **40B** ，上下文窗口 **1M token** 。架构上集成了DeepSeek的稀疏注意力（DSA），保留长上下文能力的同时压低部署成本。主打编码和长时任务。

官方对5.2的介绍相当克制，没甩一堆跑分，只说「在5.1基础上强化了编码能力」。

![GLM-5.2官方工程能力评测](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zn6JLNTpYFFNMMicCdf6s5ib3aQDAiaLgmphibgZxuaHR52IlibeqNCHVMkadeWzHeuzm6URapzrKN7DYOaVsOs9hp59VbJaVetiacFU/640?wx_fmt=png&from=appmsg)

从官方数据看，GLM-5在前端构建成功率（98%）和大仓库探索（65.6%）上跟Opus 4.5基本持平，多步链式任务（52.3%）还差一截。

祖传bug测试
-------

有个开发者手里有个祖传bug，分三层：表面问题、深层逻辑问题、引用的公共库本身有bug。三层都解决，才算过关。

Claude Opus 4.8： **100分** 。三层全解，发现库的bug后没改库，用本地业务代码规避了。耗时约 **4分钟** 。

GLM-5.2 Thinking： **96分** 。三层也全解了，但中间改错一次，自己马上意识到，自动回滚。耗时 **17分18秒** ，打破DeepSeek V4的11分钟记录。

GPT 5.5 xhigh：同样三层全解，只用了 **2分多钟** 。

MiniMax M3：同样三层全解，耗时 **7分51秒** 。

![29个模型测试结果](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmsyUK8htiaAZPhLkEbCXqnoTJexGXq3I3nicxsnJ8hdpgJv4AZRhOsjeKY45sTyNA91cIuic1Uu1icWPmZicPjiaOnALDLKiaNUzZM94/640?wx_fmt=png&from=appmsg)

能发现三层bug的模型一共就5个：GPT 5.5、Gemini 3.1 Pro、Opus 4.7、DeepSeek V4 Pro、GLM-5.2。国产模型第一次站到这个行列里。

但差距藏在过程里：Claude和GPT处理这种问题，一步到位。GLM-5.2是拼了命才做到的。结果一样，过程完全不同。

横评结果
----

同一套闭源项目，两个测试题，不开新上下文，5个模型跑。三个独立模型分别打分再归一化，从代码正确性、工具调用规范度、上下文利用率、任务完成度四个维度评，满分100。

参赛选手：GLM 5.2 + ZCode、GPT 5.5 + Codex、Gemini 3.5 Flash + Antigravity CLI、Composer 2.5 + Cursor、Kimi 2.6 + Claude Code。

![测试架构](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9znAuNWqozzUwfRhYKBLl7WFhlnqBBDa5fKkx7vN45RtBs8ymR3xaEdruqLXEZFWKu3lg83Kx50lOf5xN2iavnnnicT5m4yM7s4p0/640?wx_fmt=jpeg&from=appmsg)

三个模型分别打分，做归一化复核。

![横评结果](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zkXRSBug0qbVwqLPU8LY448HoNSu025rlWXXex0Rz4M19ulwuFduEur7h3ibB1GibqWFkStWAgR2jmCwmmI44OcGc2Wlf3m4ib7do/640?wx_fmt=png&from=appmsg)

Composer 2.5排第一。

就是Cursor里那个基于Kimi 2.5蒸馏的模型，干翻了GLM 5.2和GPT 5.5。

速度差距也大：Composer 2.5用了 **8分钟** ，GLM 5.2和GPT 5.5都用了 **40分钟** 。

原因不难找：Cursor手里有全球最大的高质量代码数据集，几百万开发者每天写的真实代码，加上Colossus 2的百万H100集群做后训练。底子是Kimi 2.5，但喂的数据和算力完全是另一个量级。

![Colossus 2算力集群](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zkGpRPjaex8CBiaiaq7jJwHiaP6CbUHxthsbREt0zZOXtsMQpnxGhGqico5s6GiaX6Npe6TSPJFiatnbMSvQ5ZLcf66TFuv1oUEZ5F8w/640?wx_fmt=png&from=appmsg)

Cline官方公布过生产数据：Kimi系在diff编辑上的失败率只有 **3.3%** 。这不是跑分，是上千用户真实生产环境里的数字。

8个Benchmark全面对比
---------------

![GLM-5.2 vs 其他模型8个Benchmark对比](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlKAicu34w4pKc2diajGibaN3ia5WBn6mNBXE7PP6UlpwibVHwY7OpXoNjmfqGNbSanWQs8vHjYKSWDmKaUyQl2eSHz35CCFlxddyO8/640?wx_fmt=png&from=appmsg)

GLM-5在Humanity's Last Exam上拿了 **50.4分** ，超过Opus 4.5的43.4分。BrowseComp也领先（75.9 vs 67.8）。但在SWE-bench Verified上，Opus 4.5以 **80.9分** 领先GLM-5的77.8分。

8个benchmark里，GLM-5有3个超过Opus，3个接近，2个有差距。总体来看，已经到了同一个档次。

接入实测
----

最较真的做法：同一个agent、同一套工具、同一个真实项目、同一批指令，只换后端模型，拿Opus 4.8当尺子。

五个任务逐个过。

读懂陌生项目这步，MiniMax出方案最快，MSA长上下文加速确实管用；GLM方案最克制、最贴意图；Kimi因为256K窗口最小，一开始就跟不上。

多文件接口开发这关，Kimi反超了。工具调用是Kimi系的强项，diff干净、几乎不空转。GLM紧随其后但慢。MiniMax太主动，会顺手把相邻代码也「优化」一遍。

修并发bug是最硬的一关。GLM推理在国产里数一数二，定位逻辑严谨，但最隐蔽的并发竞争点还是要人给提示。三家离Opus都有看得见的差距：那个状态竞争点，Opus不用提示就咬住了。

长会话重构这步，GLM的1M上下文最实，四五十万token挂着不掉链子。MiniMax的MSA让长上下文又快又便宜。Kimi的256K最先触顶，压缩后偶尔忘了前面的约定。

最后压工具调用。Kimi最规范，格式错最少。GLM稳但慢。MiniMax偶尔自己加戏发冗余调用。

工程评测
----

公开的工程能力评测榜上，GLM-5.2在5个工程中拿了3个A档，持平Opus 4.8。

![Nao佬工程评测榜单](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmZ5ricNtXaNMQhOULN9HExibiaxiciaRo2pb61e14dHA5I7GlLbN7Pibp5gwVgvJsEuuFhBbGZGc3TK8StuDlA99UuuCBUYJD51DLtQ/640?wx_fmt=png&from=appmsg)

A档意味着模型几乎不犯错，需求理解一步到位。GLM-5.2前代5.1连5个项目都完不成，5.2一次性全过了。

但有个细节：同样完成F项目，Opus 4.8用了564次tool calls、输出260K，GLM-5.2用了557次tool calls、输出仅170K。消耗更低，但这是在GLM开max档位、Opus开high档位的错位对比下。

在小众技术栈上GLM还是会翻车。遇到不熟悉的三方库API，GPT会大量搜官方文档demo，GLM靠试错和推理硬趟。配上明确的文档补充，表现会好很多。

怎么选
---

测完一圈，国产模型的能力到了「能用」的级别，但离「好用」还差一口气。

这口气差在体感，不是跑分。

GLM-5.2推理确实强，三层bug能自己回滚，工程评测拿了3个A档。但 **17分钟** 跑完一个测试，Opus只要 **4分钟** 。日常开发里，等17分钟和等4分钟，是完全不同的工作节奏。

Composer 2.5速度最快，8分钟跑完横评，代码质量还排第一。但它是个蒸馏模型，复杂推理还是会露馅。简单活一把过，难一点的就要人盯着收尾。

Kimi K2.7 Code工具调用最稳，diff编辑失败率3.3%。但256K上下文是硬伤，项目一大就触顶。

MiniMax M3长上下文又快又便宜，但太爱加戏，会顺手优化你没让它动的代码。

没有一个模型能通吃所有场景。

现在最实际的用法是把Claude Code当底座，后端按任务换。攻坚活用Opus，量大的日常活用GLM的Coding Plan（ **18美元/月** ），工具密集的编辑任务临时切Kimi。

日常80%的活国产模型已经可以了，剩下20%的硬骨头目前还得靠Opus。但这个比例在变，半年前是0:100，现在是80:20。

回到开头的问题：GLM-5.2这次真超Opus了？

没有。但已经到了同一个档次，差距不在能不能做到，在做到的方式和速度。

⭐如果你希望下次也能接受到此等质量的好文 请务必将我们星标，防止迷路！转给你的朋友一起变强！

[Fable 5被大神攻破，美国选择一刀切：非公民全禁](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485948&idx=1&sn=90e51f88e4693847d565ad9fd42b583b&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言