     Gemini接管「谷歌帝国」 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

Gemini接管「谷歌帝国」
==============

原创 阿竹 AI飞升录 2026-05-21 19:22 浙江

> 原文地址: [https://mp.weixin.qq.com/s/IRLZtYiSR-\_FnU8BfpTwNA](https://mp.weixin.qq.com/s/IRLZtYiSR-_FnU8BfpTwNA)

5月19日Google IO开完。

5月21日，Antigravity宣布Gemini模型速率限制提升3倍、本周配额全部重置。两天就服软，说明用户反弹比Google预想的严重。

但额度不是重点。重点是Google这次发布会透露出来的战略意图。

模型发布
----

**Gemini 3.5 Flash。**  价格输入$1.5/输出$9，比上代涨了3倍。速度官方说300tps，但flash系列有降速惯例——IO大会前实测1000tps，第二天OpenRouter渠道降到81tps。

纸面成绩：工具调用（MCP Atlas）83.6%，超过GPT 5.5的75.3%。多模态理解83.6%，超过GPT 5.5的81.2%。输出速度是其他前沿模型的4倍。

但GPT 5.5在代码执行（78.2% vs 76.2%）、长上下文定位（94.8% vs 77.3%）、抽象推理（84.6% vs 72.1%）上仍然领先。

能力侧重点不同。Flash强在速度和工具调用，GPT 5.5强在代码和推理。

![Theo的成本分析推文](https://mmbiz.qpic.cn/sz_mmbiz_jpg/JYWVQlsu9znVlR9Myk4pxXC8v9mNsBsojicba2rf5k1icm8Ls14ic2pHFq3QjibmBaPgURV3KOSoXMd4MIcNx9Iw5jXjPZgvrKcXIo1Picuia4AiaI/640?wx_fmt=other&from=appmsg)

成本方面有个容易被忽略的问题。X上网友Theo指出：Flash看起来便宜，但太吃token。Artificial Analysis测试里，GPT-5.5 Medium用约2200万token、成本1199美元、得分57；Flash用约7300万token、成本1522美元、得分55。单价低，但总成本未必便宜。

![各模型智能vs成本散点图](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9zm2amLd1J48Htrk6ymlqWx2afJNPZZPZ3tHctticC0H7oFsUewD75WRatSS5x2vlILUvUMuB3tPauhTwEs3SJsqdtWlr9auLU2g/640?wx_fmt=other&from=appmsg)

3.5 Pro没发布，预计6月上线。

**Omni Flash视频模型。**  每次消耗10-30积分，Pro会员每月1000积分。支持自拍角色和可编辑性，4-10秒。目前整体性能在Seedance 2、Kling、MiniMax之后。

**Gemini Spark。**  Gemini app里的个人AI智能体。跑在Google Cloud虚拟机上，24小时服务，支持MCP接入第三方工具。结合Gmail、Calendar做旅行规划、约会安排、信息整理。核心优势建立在Google生态上。5月底上线，初期仅限Ultra用户。

**智能眼镜。**  Google+三星+高通联手，音频眼镜和显示眼镜两种形态，今年秋天上市。

额度风波
----

IO大会前后，Google开始从拼模型转向控成本。Flash看似便宜但极度耗token，总成本反而更高；同时Pro用户用量接近Ultra却付费更低，资源结构失衡。

Google对会员体系做了调整：新设Ultra $100会员（相当于5x），老Ultra $250降到$200。Pro会员额度从Ultra的1/5调整到1/20。

这些调整引发了用户反弹。Reddit的Gemini板块出现大量关于额度缩减的讨论。

5月21日下午1点，Antigravity负责人Varun Mohan发推：所有付费层级Gemini模型速率限制提升3倍，本周配额全部重置。9.2万人围观。

![上传图片](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zltAI6qLdel2BichC2LDSiaxCRkp375j7a8xlA4MBicKYKXtVuicEzXj5euiaPAAp0P7DgqCYKRNmDy8f3wJxWWh5ehvbwAY6Q9qVUk/640?wx_fmt=png&from=appmsg)

Antigravity三件套
--------------

这次Google把Antigravity拆成三款产品，分别对标市场上的不同竞品。

**Antigravity 2.0（桌面客户端）**  对标Codex App和Claude Desktop。独立App，不再是VSCode Fork。支持创建对话、管理项目、设定时任务。

![Antigravity 2.0桌面客户端界面](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmLLSLzy9wmQnRgUNSdHQqAVicNQLKibTkcbusaV22G6ezJ89UIWCe0ZLIb3DvSyHx5dGib3UfXVto4MjuH3dryOZicicqTgJmDibQ5g/640?wx_fmt=png&from=appmsg)

升级后有两个坑：Google账号可能登不上（退出重登或换网络），IDE被拆成独立App了（需要单独下载）。

**Antigravity CLI**  对标Claude Code和Codex CLI。把原来的Gemini CLI升级成Antigravity CLI，用 `agy` 命令启动。支持 `/goal` 命令自动拆解目标。Gemini CLI六月停服后由这个接替。

![Antigravity CLI界面](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlesQNwrfglCqhcEj36mUXQZz8EtnlduUd70UHE8dJe0SfPZvKQN2qtuuZaIOrXI17cLx6Pia7ia6SRbghMcHpZ9LXeHaMkwG8eU/640?wx_fmt=png&from=appmsg)

安装步骤：

**macOS/Linux：**

`curl -fsSL https://antigravity.google/cli/install.sh | bash`

**Windows PowerShell：**

`irm https://antigravity.google/cli/install.ps1 | iex`

**Windows CMD：**

`curl -fsSL https://antigravity.google/cli/install.cmd -o install.cmd && install.cmd && del install.cmd`

注意：CLI需要先用Antigravity账号或IDE完成登录验证。 `agy` 命令找不到的话，手动 `source ~/.zshrc` 再试。

**Antigravity IDE**  从主客户端拆出来独立App，专门写代码。目前Claude Code和Codex没有类似的独立IDE产品。

不想装任何东西的话，可以用第三方平台ZenMux直接体验3.5 Flash，兼容主流API格式，现在限时免费试用。

竞争格局
----

编程Agent市场：Claude Code第一，Cursor/Codex第二梯队，Antigravity第四。

2C Chat：GPT第一，Google第二，市占率约为GPT的50%。

文生图：GPT-image-2第一，Google第二。

文生视频：Seedance 2第一，Google第四五。

推理芯片：Nvidia第一，Google第二。

AI云服务：AWS第一，GCP前三。

**单看每一个产品，Google都未必绝对领先。**

但这件事要换个角度想。

Google可怕的地方，不是它每一次都第一个做出新东西，而是它手里有入口。PC时代微软有Windows，办公时代有Office，开发者生态里有GitHub和VS Code。产品一旦被塞进体系里，意义就完全不一样，不是单独跟你拼功能，是把功能变成系统默认的一部分。

Google现在做AI，也是这个逻辑。

3.5 Flash、Spark、Antigravity、智能眼镜，单看每一个都未必最强。但一旦放进搜索、Chrome、Gmail、Calendar、YouTube、Android这些入口里，AI就不再只是一个你主动打开的聊天框，而是变成一种默认存在的能力。

搜索的AI Mode月活已经突破10亿。Gemini app月活突破9亿。AI Overviews月活超过25亿。这些数字说明：Google离用户最近。

所以真正重要的，不只是哪个模型跑分第一，而是谁离用户最近。谁能出现在用户搜索、写邮件、看视频、写代码、安排日程、打开手机的那一刻，谁就有机会重新定义下一代AI产品。

Google在每个细分市场都不是第一，但它在所有入口都有位置。这就是它最大的底牌。

[手慢无！Gemini Pro即将升值，白嫖4个月最后窗口](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485380&idx=1&sn=0cf0f16612e35c7a4d0bf99a3e91418e&scene=21#wechat_redirect)

  

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言