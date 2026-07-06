     来了来了，Claude Code 泄露源码深度拆解，附源码架构 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

来了来了，Claude Code 泄露源码深度拆解，附源码架构
===============================

原创 阿竹 AI飞升录 2026-04-02 20:19

> 原文地址: [https://mp.weixin.qq.com/s/nCfSzY4Vsohqu50RNRT9Bg](https://mp.weixin.qq.com/s/nCfSzY4Vsohqu50RNRT9Bg)

三月底发生了一件挺戏剧性的事。
===============

Anthropic 往 npm 发包的时候，忘了删 `.map` 文件。就这么一个低级操作，51.2 万行 TypeScript 源码直接全曝光了。半小时内，克隆源码的 GitHub 项目星标冲过 5k，全网疯狂围观。

有意思的是，就在这之前两周，他们刚因为 CMS 配置错误泄露了下一代 Mythos 模型的信息。两周两次，确实有点草台班子的意思。

![Claude Code 架构封面图](https://mmbiz.qpic.cn/mmbiz_png/blAARj1FkxnCYw7iaiaiam52ChE6beHnIDgPunkaonHibpAlfNnSfBAg9dMrkARs7y0HH2UwdReFcz6ibrh0zogGU6nq1YjCCUHicGxjjvmCFnFKE/640?wx_fmt=png&from=appmsg&tp=webp&wxfrom=5&wx_lazy=1#imgIndex=0)

当然，全网讨论最多的是那些隐藏功能——会在半夜自己整理记忆的 KAIROS 助手，终端里长着赛博宠物的 BUDDY，还有 Undercover 模式（Anthropic 员工给开源项目提 PR 时自动抹掉 AI 痕迹）。

我自己翻完这批代码之后，感受有点不一样。那些隐藏功能固然好玩，但真正有意思的是它的工程架构——它暴露了一件事：AI Agent 能不能上线扛活，门槛在系统工程，不在 Prompt 技巧。

这套东西按平台设计，不是小工具
---------------

光看目录结构，就知道野心不小。

入口、任务、工具、调度、记忆、插件、Hook、MCP 全是独立层，边界划得很清楚。40 多个工具模块独立封装，核心推理逻辑 `QueryEngine.ts` 一个文件就快 5 万行。

很多工具死在扩展的时候。今天只做 CLI 够用，等你要接 IDE、接自动化流程、接团队协作，单体结构会立刻撑不住，整仓库翻修。泄露代码里已经出现了 `coordinator`（多智能体协调器）和 `bridge`（连接 VS Code / JetBrains 的桥梁），就是提前把扩展位留好。

还有一个细节：启动阶段就并行做配置和密钥预取，把等待时间提前消化掉。用户感知到的是"它回得快"，背后是毫秒级的预算分配。

Prompt 管理的本质是配置管理
-----------------

很多文章讲 Prompt 只讲"写什么内容"，很少讲"怎么控成本"。

这套架构里的做法是：把稳定内容和会话内容拆开，固定边界，让前缀缓存尽量命中。缓存命中率一旦上去，延迟和成本同时下降，高频场景才跑得起来，不会被 token 账单拖死。

有个坑特别隐蔽：字段顺序变化就能打穿缓存，成本可以在一周内飙好几倍。你不会收到任何报错，就是账单突然变大，然后才开始找原因。

改动有无日志，边界有无约束，命中率有无持续观测——这些事情没做，Prompt 写得再漂亮也没用。

工具调用的治理链，六级权限验证
---------------

这是整套架构里最被低估的部分。

Agent 危险的地方在于它有执行力——能跑命令、改文件、调外部服务。泄露源码里有一套六级权限验证系统，每一次工具调用，无论是执行 Shell 还是读写文件，都得先过这套验证。

完整的链路至少要有四层：输入校验、权限决策、风险预判、失败补偿。再往上加执行前后的 Hook 和审计追踪，才算有资格讲"可控自动化"。

见过这种情况——模型改了一个不该改的配置，服务没挂，但指标全乱了，后面花两天回溯。问题就在没有留痕：不知道它改了什么、什么时候改的、为什么改。治理链平时看起来多了几步，出事时是唯一能救命的东西。

新模型接入的工程代价，源码注释里写着
------------------

泄露源码里有一块让我反复看的内容，是关于新模型接入的工程代价。

换模型不是改个参数名这么简单。实操里最麻烦的是行为边界变化：

*   空工具结果触发假结束
    
*   `tool_reference`
    
     在尾部诱发异常停止
    
*   模型回退时签名块不兼容
    
*   false claim rate 静默升高
    

这类问题的特征是：模型没坏，系统也没坏，组合在一起会坏。单看任何一层都正常，问题藏在层与层之间。源码注释里工程师自己坦诚写着这些代价，能看出来都是真实踩过的坑。

每次模型更新都需要灰度和回滚开关，不然上线就是在抽奖。这件事不是有条件再做，是必须在前面设计好的。

多 Agent 的正确顺序：先隔离，再并发
---------------------

泄露代码里有 Coordinator Mode，能让主 Claude 实例调度多个并行子 Agent。

很多团队一上来就追并发，结果主对话被试错垃圾塞满，越跑越偏。

正确顺序是先做隔离。探索、实现、验证三个角色分开，在不同上下文里运行。只读探索角色最关键——只找证据、做归纳，不允许写入，把大量无效路径挡在外面，不污染主流程。主线程只接结论，上下文才能保持干净。

隔离做完，再叠缓存复用，子任务开得再多，成本才不会无上限膨胀。这个顺序反了，之后很难补救。

每周过一遍的检查单
---------

把以上内容压成 6 条，做 Agent 项目时定期核对：

1.  Prompt 是否有稳定边界，缓存命中率是否可观测
    
2.  工具执行是否全链路留痕，失败后能否快速回溯
    
3.  高风险动作是否统一经过权限层，不允许直通执行
    
4.  探索 / 实现 / 验证是否角色分离，验证结论是否独立产出
    
5.  新模型上线是否有灰度和回滚开关，异常能否分钟级止损
    
6.  上下文是否有压缩策略，长任务会话是否仍然清晰
    

拿这 6 条去看任何 Agent 产品，很快能判断它是"看起来聪明"，还是"真能上线扛活"

最后把资料放这。这次源码泄露之后，博主 XiaoTan 在 X 上整理了一份《ClaudeCode 源码深度研究报告（增强完整版）》，比大多数分析文章要系统得多。

![Claude Code 源码研究图](https://mmbiz.qpic.cn/sz_mmbiz_jpg/JYWVQlsu9zlJ2sk5LInDVQTd3Np3NaSEOgpECmIhM4sWxaxAIGQGSYbP0mYvdo0PPicXj2T91SFejibEp2nBdnOPLcG3Z8ULH7ZS0czhL2vo4/640?wx_fmt=jpeg&from=appmsg)

下载链接：

\[https://github.com/tvytlx/ai-agent-deep-dive/raw/main/ai-agent-deep-dive-v2.pdf\\\](https://github.com/tvytlx/ai-agent-deep-dive/raw/main/ai-agent-deep-dive-v2.pdf)

如果你在公众号里看这篇，也可以直接回复：`claude code，`拿同一个 PDF。

⭐以上，既然看到这里了，如果觉得不错，随手点个赞、在看、转发三连吧，谢谢你看我的文章，我们下次再见。

  

[刚刚，Claude Code源码泄露了](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485130&idx=1&sn=cf41c64c8543c7b1be1f26d717834977&scene=21#wechat_redirect)

[Claude Code 创始人最新15条技巧，看到这个帖子才知道自己只用了20%](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485063&idx=1&sn=890106467a11bfac22dee3dc171bb818&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言