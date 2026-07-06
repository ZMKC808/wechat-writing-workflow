     3天54k Star！Karpathy让AI自己做科研去了 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

3天54k Star！Karpathy让AI自己做科研去了
=============================

原创 阿竹 AI飞升录 2026-04-03 11:57 浙江

> 原文地址: [https://mp.weixin.qq.com/s/wfe5KXEtsoAnw1D-supOxw](https://mp.weixin.qq.com/s/wfe5KXEtsoAnw1D-supOxw)

Karpathy在GitHub扔了一个新项目，叫autoresearch。

没有发布会，没有论文，就一条推文加一个链接。但三天之内涨了54k Star，冲上GitHub Trending榜首。

我点进去看了一下README，第一段话有点意思：

"曾经，前沿AI研究都是肉做的计算机在吃饭、睡觉、玩耍的间隙完成的，偶尔通过声波互联进行'组会'这种仪式来同步进度。那个时代已经一去不复返了。"

![图片](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlW5cRnX5iaoibtKriahtibcxOpz4rlDavicsyd4Hn9teVCTrBoaL5UQqQZJ9MvrxLVvtyFqrpOIWl1Te87CwpkWGdIdsSia3RgiadPhY/640?wx_fmt=png&from=appmsg)

* * *

**这个项目在做什么**

一句话：给AI一个真实的训练环境，让它自己改代码、自己跑实验、自己判断结果好不好，然后一直循环，不用人插手。

每次实验固定跑5分钟。改了代码跑一次，结果变好就保留，变差就撤销回去，再试下一个想法。按这个节奏，一晚上能跑将近100次实验。

你去睡觉，它在做科研。

**整个项目只有三个文件**

这是我觉得最值得说的部分，因为它极简到有点反直觉。

`prepare.py：`定规矩的。数据怎么准备、用什么指标评估、训练时间上限——全在这里，固定死，AI不能碰。

`train.py：`AI唯一能改的文件。模型结构、优化器参数、学习率、层数——想怎么改就怎么改，只要最后指标变好。

`program.md：`你写给AI的工作手册。用普通文字告诉它：目标是什么，哪些东西不能动，什么算有效改进。

Karpathy原话是：人类迭代`.md，`AI迭代`.py。`

我第一次看到这个分工的时候停了一下，因为它说清楚了一件事：你不是在写代码，你是在写"怎么指导AI做研究的说明书"。这个说明书写得越好，AI跑出来的结果越好。

**评估指标只有一个：val\_bpb**

这个词看着陌生，但逻辑很简单：衡量模型预测文字的准确程度，数字越低越好。

选这个指标的原因是它跟词表大小无关。AI改了模型结构、换了分词方式，照样能拿这个数字做公平比较。

Karpathy跑了一次，AI做了126次实验，val\_bpb从0.9979降到了0.9697。

**然后是让他自己有点意外的部分**

他把autoresearch指向了自己手调了很久的nanochat代码，让AI跑了两天。

AI做了700次实验，找到了大约20个有效改进，全部可以叠加，也可以迁移到更大的模型上。最终结果是"训练到GPT-2水平所需的时间"从2.02小时降到了1.80小时，提升了11%。

他自己说，这段代码他已经手动调了很长时间，以为差不多到头了。

AI找出来的具体问题里有几个挺具体的：他的attention没加scaler multiplier，导致注意力太分散；Value Embeddings没有加正则化，他说这是他自己的疏漏；AdamW的betas参数设置也有问题；带状注意力调得过于保守。

这些不是模糊的"优化空间"，是实实在在的代码问题。做了20年AI的人，被自己写的程序翻出来的。![图片](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zn5HN7lic14d7VJnjmfuRd2oibgfz2Rnr1h6nLShh33CzRlHOyGPOFWCFb0jkhW5aMncemDRz4libhThyT1vyWufiaNMeBylHxo9jw/640?wx_fmt=png&from=appmsg)

* * *

**真实跑起来是什么感觉**

有人在Mac Mini M4上试了，跑了35次实验，26次失败或崩溃，7次成功。

成功的那7次结论是：模型变简单了，效果反而变好了。

这个结论没有人提前设计，是AI自己跑出来的。

失败率高不高？高。但它一晚上跑35次这件事本身，换人来做需要多长时间？

**没有H100怎么办**

Karpathy在README里写了小算力的调整建议：

数据集换成TinyStories，这是GPT-4生成的儿童故事集，内容窄、熵低，小模型也能跑出像样的结果。词表大小从8192往下调，256到4096都可以试。序列长度MAX\_SEQ\_LEN降到256。模型层数DEPTH从8降到4。

不需要H100，普通GPU能跑，Mac也有人在试。

**怎么启动**

  

`# 安装uv   curl -LsSf https://astral.sh/uv/install.sh | sh      # 安装依赖   uv sync      # 数据准备（跑一次就够）   uv run prepare.py      # 测试跑一次   uv run train.py   `

然后在仓库里打开Claude Code或者Codex，输入：

  

`Hi, have a look at program.md and let's kick off a new experiment!   `

去睡觉就行了。

**它的边界**

现在只支持单张NVIDIA GPU，不支持分布式训练。Mac和CPU理论上能改造支持，但Karpathy说那会让代码变复杂，他不想动。

5分钟实验周期也意味着，需要长时间训练才能验证的想法，它处理不了。

Karpathy说他下一步想让多个Agent并行协作，像SETI@home那样，每个Agent跑不同的研究方向，通过GitHub的Discussion互相读取结果、交叉启发。他自己描述的目标是：不是模拟一个PhD学生，是模拟一整个由无数PhD学生组成的研究社区。

项目地址：github.com/karpathy/autoresearch

⭐以上，觉得有用的话点个赞在看，我们下次见。

[来了来了，Claude Code 泄露源码深度拆解，附源码架构](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485155&idx=1&sn=7fcbbbce29285639dfe26791833b1dfb&scene=21#wechat_redirect)

[刚刚，Claude Code源码泄露了](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247485130&idx=1&sn=cf41c64c8543c7b1be1f26d717834977&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言