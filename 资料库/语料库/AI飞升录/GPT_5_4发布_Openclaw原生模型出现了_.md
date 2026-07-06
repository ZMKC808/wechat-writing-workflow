     GPT-5.4发布：Openclaw原生模型出现了！ \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

GPT-5.4发布：Openclaw原生模型出现了！
==========================

原创 阿竹 AI飞升录 2026-03-06 22:23 浙江

> 原文地址: [https://mp.weixin.qq.com/s/\_aI8DmNdcgW1Ok2HGS13jg](https://mp.weixin.qq.com/s/_aI8DmNdcgW1Ok2HGS13jg)

3月5日 OpenAI 发了 GPT-5.4，ChatGPT、API、Codex 都上了。通稿里一堆能力升级，我扫完发现有个点挺少人聊：竞争焦点已经从窗口有多大，转到了上下文怎么用。

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmUaOb00WkicWStUz4mruMyCztZDRCth70CC0fEt2Ju61ReFiah2ufQNcfKbECLdQ4JqJj7iaOjW958dOOpesWtKwicGicahthdlm6U/640?wx_fmt=png&from=appmsg)

以前大家比的是谁家能塞更多 token，现在窗口都百万级了，光会堆 prompt 不够。你得知道什么该塞、什么不该塞，什么时候按需拉、什么时候提前锁。模型对中间部分容易失焦，塞得越多不一定越好，有时候反而拖后腿。GPT-5.4 在这块动了几刀，工具搜索、阶梯定价、思考预览、原生操控，都在往同一个方向推：别堆，要精。

下面展开说说。

工具搜索：按需加载，Token 省一半
-------------------

做 Agent 的都有体会，工具一多，prompt 就炸。几十个 MCP 服务器一挂，每个请求多几千上万 token，绝大多数用不上，钱照花。以前的做法是每次对话开始前，把所有工具的说明一股脑塞进去，不管这次用不用得上，Token 先花了再说。工具一多，prompt 就变成几万 token 起跳，响应慢、成本高，模型还容易在无关信息里打转。

GPT-5.4 换了个思路：先给模型一份轻量清单，用到哪个再查定义、追加进对话。用过一次的还能直接缓存，下次不用重新拿。官方在 36 个 MCP 服务器的配置下测了 250 项任务，同样准确率下，总 Token 消耗降了 47%。将近一半，对跑量大的人来说，账单上会很明显。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9znxN9kJGBQRfMyhccPrfoBGW8a0WrNpDIvIqO9jrCH0ojWpMoqeZIgyZawkqKDSRXwruoQgCyicBPswJk6icc7ycm3heibU7nZxto/640?wx_fmt=png&from=appmsg)

背后的逻辑不复杂：模型注意力有限，塞一堆用不上的东西，有用的反而被稀释。按需检索，信号就清晰多了。我试过把一堆 API 文档一股脑塞进去，和只塞当前任务相关的几段，效果差一大截。GPT-5.4 这个工具搜索，就是把这套逻辑做成内置能力了。以后做 Agent 的，工具多了不用再硬着头皮全塞，可以试试按需加载。

阶梯定价与 272K 分界线
--------------

GPT-5.4 支持 105 万 token 上下文，但超过 272K 的部分按两倍计费。乍看是涨价，其实是在推你一把：别什么都往里塞。

整本代码库、几百页合同一股脑塞进去，看起来省事，但模型对中间部分容易失焦，准确率反而掉。有个说法叫上下文腐烂，窗口越大，模型对中间部分信息的召回能力越差。用工具搜索、缓存、按需加载，只把关键信息留在上下文里，反而更划算。缓存输入有 90% 折扣，高频用的基础上下文（比如你们公司的合规红线、代码库索引）可以锁在 GPU 里，重复请求延迟能降不少，多轮对话时不用每次都重新算一遍。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9znEYNjqYlbbwohK8FN7oPTIIPOAjcWzGIDE3fkObXudJxTQnEESjzjbFF81s9KvcwibjNEHMHUTITzYKwKZhH9WMlY5LwZhmGZE/640?wx_fmt=png&from=appmsg)

从测试结果看，128K 到 272K 是表现最稳的区间，512K 以上准确率会下滑，1M 区间更接近实验性质。窗口大是一回事，用得好是另一回事。我见过有人为了省事把 100 万 token 全塞进去，结果中间部分模型跟没看见一样，白花钱。日常用的话，控制在 272K 以内比较稳妥，真需要超长上下文，得针对具体任务验证一下效果。

思考预览与中途纠偏
---------

用过 AI 处理长任务的人大概都有过这种体验：等模型跑完一大段，发现方向错了，只能从头来，时间全浪费了。GPT-5.4 Thinking 多了个思考预览：执行复杂任务前，先简要说明打算怎么干，再开始执行。

用户可以在生成过程中随时打断、补充指令，模型会动态调整后续逻辑，不用等跑完再开新一轮对话。计划偏了可以立刻拉回来，这种体验差别挺大的。比如你让它规划一趟旅行，跑着跑着发现它偏向飞，你想自驾，以前得等它跑完再重来，现在中途插一句就行。又比如做财务建模，模型跑着跑着用了你不想要的假设，以前得等它跑完再重开，现在可以中途纠偏。对需要多轮协作的 Agent 任务来说，迭代周期缩短了。

![图片](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zkAZ2mZ2uiax5vibC6bD9ibicAYBW1Xf0sF1COpiaKaeJRWkT2RdJrDcOzNSrSNAIqibyESXlnve1v3ianNdpRb9ytZTJ0Jibkl6ftSa3M/640?wx_fmt=png&from=appmsg)

Playwright Interactive 也是这个思路：边写代码边在浏览器里测，模型同时当开发者和测试员。主题公园模拟游戏就是典型案例，从提示词到可玩 demo，全程自己完成。边造边测，出错能早发现，不用等最后验收才发现一堆 bug。GPT-5.4 把 Codex 的编程能力并进主线了，SWE-Bench Pro 上跟 Codex 持平，知识工作还比 5.2 强，写代码、写文档、做表格都能在一个模型里搞定。

原生操控电脑
------

GPT-5.4 是 OpenAI 第一款把计算机使用能力原生内置的通用模型。以前操控是独立模块，跟语言理解、代码生成各干各的，信息来回传，效率自然打折。现在用截图理解界面、发鼠标键盘命令，都走模型自己的推理，不用再绕一圈。它能根据屏幕截图理解软件界面，然后执行鼠标点击、键盘输入，在 CRM 里提订单、在 Excel 里做报表、在 Outlook 里发邮件，这类跨应用的复杂流程可以一气跑完。

OSWorld 测桌面导航，GPT-5.4 成功率 75%，人类基线 72.4%。Mainstay 拿它做三万个物业税务门户的自动填表，首次成功率 95%，三次以内 100%，会话速度提升三倍，Token 消耗降了 70%。操控电脑这类场景，多了一个可选的基座。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zkicptiaS8UlS2MtWiaxvyBT44miaUnRuWnbWrO6VmRwjeNG1KVTCcemj6yN4k2CicibZlvDL9Ven7SwPPKul6V1lvsUz2lfpPQcwnj8/640?wx_fmt=png&from=appmsg)

玩 OpenClaw 的可以留意，GPT-5.4 支持 Codex 登录后，操控这块会有提升。

知识工作与专业场景
---------

GDPval 测 44 种职业的真实工作任务，GPT-5.4 拿 83%，十次里有八次以上能跟专业人士持平或更好。投行建模、法律合同审计、医疗辅助，都在往能独立完成整块工作的方向走。OpenAI 内部测投行建模，三张表模型准确率从 5.2 的 68% 涨到 87%，法律平台 Harvey 的 BigLaw Bench 上 GPT-5.4 拿 91%。幻觉率比 5.2 低，单条陈述出错概率降 33%，完整回复含错概率降 18%，专业场景对准确性要求高，每降一个点都能多开一些应用。

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9zl9GzicMnUhS7Bk20czSn9DNYC0HjItcLVibI2uAKJkeuibpaqSMrwQnMFe2n2VMsXep7kHibdBX1hHhsaKpp2LOzVQElc2B9hicIFY/640?wx_fmt=jpeg&from=appmsg)

BrowseComp 测网页搜索，GPT-5.4 拿 82.7%，比 5.2 高 17 个百分点，Pro 版更到 89%。需要多轮检索、从一堆网页里筛信息的问题，GPT-5.4 会持续搜下去，不会轻易放弃。

整体来说，GPT-5.4 把编程、推理、操控、搜索、长上下文都塞进一个模型了，单项没缩水。但这次更值得关注的，是它怎么处理上下文：工具搜索、阶梯定价、按需加载、思考预览，都在推同一个方向——别堆，要精。

2026 年的竞争焦点，已经从模型训练转向上下文编排和工具集成。会用这套上下文能力，能在降成本的同时，解锁以前做不了的自主工作流。GPT-5.2 Thinking 保留到 6 月 5 日，之后正式退役。定价比 5.2 涨了，具体看官网。用 OpenClaw 的等支持后可以试一下，其他做 Agent 的也值得看看。

  

2026年，还会发生什么呢？

好了。

以上，如果你看到这里了，觉得不错，随手点个赞、在看、转发三连吧，如果想第一时间收到推送，也可以给我个星标⭐～

谢谢你看我的文章，回见👋

  

  

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言