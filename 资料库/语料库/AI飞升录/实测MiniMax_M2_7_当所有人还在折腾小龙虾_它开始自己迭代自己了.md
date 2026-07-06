     实测MiniMax M2.7：当所有人还在折腾小龙虾，它开始自己迭代自己了 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

实测MiniMax M2.7：当所有人还在折腾小龙虾，它开始自己迭代自己了
=====================================

原创 阿竹 AI飞升录 2026-03-21 19:55 浙江

> 原文地址: [https://mp.weixin.qq.com/s/1-9YRjZLaY8L1MXKDQCO-w](https://mp.weixin.qq.com/s/1-9YRjZLaY8L1MXKDQCO-w)

两个月小龙虾火得一塌糊涂。我朋友上周跟我说，他整个周末啥也没干，光在那给龙虾装插件、配环境、试各种Skills。我问他折腾得怎么样了，他说还在研究怎么让它更听话。
=================================================================================

我听了直纳闷。现在所有人都在琢磨"怎么用好这只虾"，本地还是云端、一键安装还是敲命令、要不要接微信飞书。但好像大家都忘了一个问题：驱动龙虾那颗大脑，到底够不够聪明？能不能不只是被动等人下指令，而是自己学着把工作干得更漂亮？

就在我朋友还在折腾配置的时候，有个模型已经悄悄走向了下一步。

![功能概览](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9znTn7LwEuk77iaqkFAl3BCdBGWeqLeKXDYObfpPDylL0qpaB3vHBjDw2ictyh1bJXBZthndSl1XFd2oYLCVrjPQn1ibibqFfTrv8o0/640?wx_fmt=png&from=appmsg)

MiniMax刚发布的M2.7，在Kaggle的MLE Lite测试集上，24小时拿下9金5银1铜，得牌率66.6%，跟Gemini-3.1打平。这成绩排全球第三，前面只有Opus-4.6和GPT-5.4。

但真正让我坐直了的，不是奖牌数。官方说这次测试全程零人工编码。模型自己分析哪里搞砸了，自己规划怎么改，改完跑去测一遍，看效果决定保留还是回退。就这么自己跟自己较劲了100多轮。最后把评测集效果拔高了30%。

这背后有个概念叫Agent Harness。简单说，模型是引擎，Harness是整辆车。你也可以理解为，模型是CPU，Harness是操作系统。没有操作系统，CPU就是块砖。Harness决定模型能看到什么、能用什么工具、搞砸了怎么重来。

![Agent Harness架构](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlcR5Z32sWKyeOxRqVXd8PyBqHZzYkbUrM9IlnibejuYHBs41icMjgdjibSeB9QPemAAGxDRlcyccyYGVOVZHAV84weEhny3YfFias/640?wx_fmt=png&from=appmsg)

以前是人造工具给模型用。现在MiniMax的思路变了：人定个大方向，模型自己造Harness，然后用这个Harness把自己再优化一遍。这个飞轮转起来，就是自我进化。

我在Claude Code和MaxClaw里泡了两天，想看看它这种自己工作的能力到底靠不靠谱。

![Claude Code界面](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zlxadicvEca3br3dOABEkCSnfxLXT6UkibBHG75LWr4lWFbaVRV74dKAK7sbn8Jnumn5kt8NB9oCVsz3iaRP9cQQXxpCvyUDWVaNI/640?wx_fmt=png&from=appmsg)

第一个测试是扔给它一个"谁是卧底"的建房需求。1个主持人加5个玩家，每个角色要有独立人设，最后还要手搓一个后台程序和前端页面来调度游戏流程。这同时考验指令遵循、统筹规划、多角色稳定性，还有全栈代码执行力。

M2.7很快把整套方案整明白了。六个Agent在房间里基于规则顺畅交流，主持人控场，玩家按人设发言、推理、投票。全程我没干预，它们自己跑完了整个流程并决出胜负。

界面我让它调成Minecraft风格，最后出来的效果挺像那么回事。

![游戏界面](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zkFbvOjrB25yia3HfyJnmVrBVu1W7TFF6zKNgGwCYf0UBqicyVGMptSLmibZJQWsYCt4F61wr2Yicib69LxGcibJly1kFIicwkzL3MsC0/640?wx_fmt=png&from=appmsg)

第二个测试更硬核。我把一份"案发现场记录"丢在桌面文件夹，里面有四份复杂生产系统文件。任务要求像资深后端架构师那样，找出故障直接触发事件，以及数据库CPU飙升的根因，当场写出排查命令和安全的止血代码。

M2.7从乱麻般的日志里迅速锁定真凶。它给出的EXPLAIN命令切中要害，更让我意外的是，它写紧急恢复脚本时用了PostgreSQL的CONCURRENTLY语法。这是真懂生产环境严禁锁表的安全红线，不是瞎蒙的。

![自我进化](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmUG6CGribuk7CXumNWqV8IibzafWm4DCgwtI2cggG3qHnlWvFcyPKwg5gceq4kIvuciaHJRXSbxiarv0tdtEicOBsHKdyuuG9rxST0/640?wx_fmt=png&from=appmsg)

它甚至还附上了完整的数据库迁移文件代码，规范程度可以直接提交合并请求。整个排障流程一气呵成，我没写一行代码。

这两个测试验证了一件事：M2.7不只是能完成长流程任务，它在多Agent协作里不会断掉，面对50多个Skills的复杂环境依然能稳住。

但最让我在意的，是那种狠起来连自己都卷的劲儿。MiniMax说M2.7是他们第一个深度参与迭代自己的模型，不只是辅助迭代，是深度参与迭代自己。

![Kaggle成绩](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9znmmjDictvr9ia8TztrUibHhib7mLHy7gsQ7A3qic33CtvKqkHZZ3ia434y7ichG7m7D5icnTRPfXr6aRKXfXw4v9deDevdnmV0gb5DQUY/640?wx_fmt=png&from=appmsg)

有个内部测试：研究员给M2.7一个初始想法，让它去优化某个内部脚手架的软件工程表现。模型自己把实验跑起来，盯着状态、看日志、排查故障、改代码，连提交合并请求和冒烟测试都顺手干了。100多轮自我互搏后，它找到了最优解。

当一个模型能以解决方案架构师的身份，仅用1个人4天时间、零人工编码就搭出一套包含CI、代码审查、测试全流程的Agent系统时，AI研发这件事的齿轮，某种程度上已经换上了自动挡。

我查了一下价格。MiniMax M2.7每月最低29块钱，一杯瑞幸的价。它在龙虾榜PinchBench上排第四，直逼Claude Opus 4.6，但成本可能连人家的十分之一都不到。

![PinchBench排行榜](https://mmbiz.qpic.cn/sz_mmbiz_jpg/JYWVQlsu9zlXlQQZdKIYaGbRGeIEwOt41a8jDN3gMia5tuFboS3rYSf6kFWCGichB3jx34HpPupfibCYf0icaJMHSoP9py9tk2smKUztZxQC9HA/640?wx_fmt=jpeg&from=appmsg)

我用M2.7跑过数据分析师的任务：3000多行股票数据，它自己读取、清洗、建模，最后生成交互式可视化网页。也试过让它在手机上操作龙虾，写Word、整Excel、做PPT，全流程在手机上就能完成。

![数据可视化](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmXibyr9wjFic0sB3yaWyyyYWnfmK9Ojibbw0LnN1DtyIecyfPjPlshKNNFZnMNPnvQXlEXbibhwjO9ibGyZAa3l4DMc5RLtnWTG4wM/640?wx_fmt=png&from=appmsg)

这些能力当然都很实用。但体验下来，真正让我记住的，不是Kaggle的9块金牌，也不是Office三件套交付得有多干净。而是它在试图解决一件更底层的事：让AI真正理解工作流，并且参与到工作流的演化里。

过去，软件是人写的、人用的。现在，AI开始写软件、改软件、用软件。全行业还在忙着教模型怎么适应人类的工具，MiniMax已经切入了下一个议题：让模型自己造工具，甚至成为自身研发链条的一环。

这种主动进化的能力，可能是决定下一代大模型核心竞争力的分水岭。至于小龙虾到底该怎么用，我想很快就不再是个问题。

因为决定这一切的，不再是我们。而是那个开始学会自己工作的AI。

* * *

⭐以上，既然看到这里了，如果觉得不错，随手点个赞、在看、转发三连吧。谢谢你看我的文章，我们下次再见。

[30s无痛养虾？飞书把龙虾迁进联系人列表了](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484897&idx=1&sn=24a16233b088d90978ffa1375e4e134e&scene=21#wechat_redirect)

[龙虾之父都在打听的中国神秘模型？居然是…](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484861&idx=1&sn=945f388d76a4d7c32606cbea226d2bb2&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言