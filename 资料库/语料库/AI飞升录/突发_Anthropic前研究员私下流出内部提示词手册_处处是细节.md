     突发！Anthropic前研究员私下流出内部提示词手册，处处是细节 \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

突发！Anthropic前研究员私下流出内部提示词手册，处处是细节
=================================

原创 阿竹 AI飞升录 2026-03-30 11:07 浙江

> 原文地址: [https://mp.weixin.qq.com/s/uqrXRMUO83510T5Hqq3RUA](https://mp.weixin.qq.com/s/uqrXRMUO83510T5Hqq3RUA)

昨天有人发给我一个帖子，说一位Anthropic前研究员泄露了一份内部提示词手册，而且是那种外面根本学不到的、建造者自己用的东西。
=================================================================

我看完第一反应是：又是这种标题党。毕竟"内部秘籍"这类内容泛滥成灾，大部分都是把官方文档改了个包装。

但我还是挨个试了一遍。试完之后说实话有点尴尬——有几条我用了两年Claude，居然一次都没这么用过。

这10条我全记下来了，原版是英文，我照着跑了一遍，感受都写在里面。

![f9c2bfc31a989ac7b21cbdc44348ead6](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlXgLyC7OnhVu64icnRwjGnOAp2oBvpHXzwfxLo9ib6jBE96rNNnQTIYY04dYxbkh7gK4qUvp1WudaDuRmVIaxveJzPeWVtMmIJE/640?wx_fmt=png&from=appmsg)

第1条：先铺背景再提问
-----------

原版叫"情境简报"。不要上来就直接抛问题，先给模型一张地图。

  

`我的背景是[角色+处境]，已经试过[A和B]，卡在[C]，帮我理清思路。   `

我之前问Claude的方式基本是："这个代码报错怎么回事？"然后把报错贴上去。它给的答案有时候能用，有时候是通用废话。按这个格式改了之后，我发现它给的方向准了很多，因为它知道我卡在哪里，不是从零开始猜我想要什么。内部测试说这个改变能提升41%的输出质量，我没法验证这个数字，但主观感受确实差挺多的。

![3741fa2f52ef48a013eda59fe84a905f](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zk2yoh9dlhxcm5WPQ2M9lQ1Pb9hxZmWJA1B5jGqkH1vZnxLEIRRpzpMpyc2k4vlhydhW6JPeQpicDa7tR1KUQQsmQYGWvfY0ZDo/640?wx_fmt=png&from=appmsg)

第2条：不要答案，要推理过程
--------------

这条说的是在提问里加一句：

  

`给出方案之前，逐步展示你的推理，标出不确定的地方，把所有假设也标出来。   `

我试了之后发现，这个要求让输出里多出来一层东西——它会先说"我假设你的意思是X"，然后走一遍逻辑，最后给答案。好处是你能在中间发现它哪里走歪了，直接在那里纠正，而不是拿到一个答案之后不知道它的推理依据是什么。有点像找一个会解题过程的老师，而不是只给你最终答案的那种。

![3378220454870ab08afab86846b444c7](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmeoxTdOKAic9iaQWvjtKYkMCn0SHXCPYZ63PE2pibdAhM5742GdytibN1Oficu7omXmhhUdqNKFXegcztaP7qbOmRNn2rRB4CpDng0/640?wx_fmt=png&from=appmsg)

第3条：让它说实话，别软化
-------------

这条在原文里叫"诚实约束"。Claude有个训练出来的倾向——特别想帮你，帮到有时候会绕开真话，告诉你想听的那个版本。

提示词是：

  

`即使难受也要诚实。如果我的计划有致命缺陷，直说，不要软化，我宁可现在听硬话也不想以后失败。   `

我用这条试了一个我自己做了挺长时间的内容策略，感觉还不错。结果它给我列了四个我没想到的问题，其中两个后来想了想确实是真问题。有点刺耳，但有用。

![001dfbdda500807ea56b169a75d7fca7](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zlicTicUBP9FKnaVQp2OYIGsxxjGGvGTiajw5YebZzbUxDzuwlS6LxxvOzfpCY90mhz2cAtyEriazvaelv0JtlQThRiaJg60a10o28c/640?wx_fmt=png&from=appmsg)

第4条：角色要具体到让人信服
--------------

我之前让Claude扮演角色，一直用"充当一个专家"这种写法。这是最弱的。

改成这个格式才有效：

  

`你是有X年[具体经验]的[特定角色]，亲眼见过[具体失败案例]，习惯用[特定框架]思考，直言不讳，跳过常规建议。   `

我试了个极端版本，让它扮演一个见过三家SaaS公司倒闭的CTO来看我的产品思路。它给出来的角度明显和默认状态不一样，会直接说"这个功能在我见过的失败案例里通常是资源黑洞，原因是……"这种具体的东西。

![146eaa8586d3860aad4ca171d428dd70](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmO6XG1dfjZIdE0eWZIKCcZtN0Xp7CPB4m90rpbP6LxVD7ac4ib1zYuoibiaqyLAeSdCwT2dzSfYfrxibQhoDdxbtMORGvkQtllavo/640?wx_fmt=png&from=appmsg)

第5条：让它专门来砸你的方案
--------------

原文叫"魔鬼代言人"。用法是：

  

`我要分享一个计划，你的任务是把它摧毁。找出所有错误假设、被忽视的风险、可能失败的原因，别手软。   `

这条我觉得是10条里最有实用价值的一条，尤其是对那种自己做了很久、已经有点滤镜的项目。原文说Anthropic内部就是这么检验想法的——找一个专门挑刺的，比找十个全程同意的有用。我试了之后被骂得挺惨，但发现的问题都是真问题。

![f7e92a6884616646a199d50efcaeeff2](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmaMCqCz1YoDZaMRkiankeq4dNPBtUiak6Tln0o8NDicRxdLWzzyDhFkZFKF2Glf0AaIhY233HPvYyVxh9N6VGc6rhQiaic2vkdtFkY/640?wx_fmt=png&from=appmsg)

第6条：把范围锁死，不让它乱猜
---------------

Claude有一个毛病：不知道答案的时候，它会用听起来有道理的内容把空白填上，而不是说"我不确定"。这条叫"范围锁定"，就是在提问里加一句：

  

`严格限于[X背景]之内，超出范围直接告诉我，我要的是信息缺口，不是你自信的错误答案。   `

原文说这能"从源头杀死幻觉"。我理解就是把它默认的"尽量帮你"行为切换成"只说我知道的"模式。用在需要准确信息的场景特别有用，比如查某个具体版本的API或者某个法规细节。

![Image](https://mmbiz.qpic.cn/mmbiz_jpg/JYWVQlsu9zmdo1K7EgnOOW41MoTzFkNZavBpYVD9B2kE1sic55qZcPzXI7EicxnPjgbmw54mTBJrmJOoSm3zR9pNposBxe4ugv62LK1Ebb9y0/640?wx_fmt=jpeg&from=appmsg)

第7条：提前说清楚你要什么格式
---------------

这条没什么神秘的，但我之前没想到Claude在这方面能卡得这么死。格式可以限制得非常精确：

  

`结构为：1）一句总结，2）三个要点，3）一个下一步建议，除非我问，其他都不要。   `

它基本上会严格按这个来，不会多写一个字。我发现这个用来处理需要快速扫一眼的内容特别好——让它把长报告压缩成三行的时候，它真的只给你三行，不会再来一段"以上是我的分析"。

![67caa472066e5d903be8c918b70e4626](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zkkmeIrXJYyppygaqaN1wUVSUXoZibaPE3lsVIOFGB0HhrE8GAK86vz6HsQNoiavuv0Q0K9BVUXA7OX67eicdWetjEC38iaCocMPvA/640?wx_fmt=png&from=appmsg)

第8条：让它交代做了哪些假设
--------------

这条被原文称为"使用最少但最被低估"的提示词。在任何复杂回答之后，追加这一句：

  

`你做了哪些假设是我应该去验证的？如果这些假设是错的，答案会怎么变？   `

试完之后我觉得这条确实有点意思。它会把隐藏在答案下面的前提条件列出来，有时候你会发现它的整个逻辑建立在一个你根本没考虑过的假设上。原文有句话我觉得挺准：大部分计划崩掉的地方不是执行，是基础假设。这条就是专门挖那个基础的。

![ca0f62d36896c0952d872635bcc7fe86](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zkO1tdJmV3Z1Fh1R1nj7rp7S3gic2picAbjxFXvTe9R7Rws3hAWnDr93sYjkWXXI10Bddsicy61o4QEeCoA5bIDPyd0icNhenVLRvg/640?wx_fmt=png&from=appmsg)

第9条：长对话里每隔几轮压缩一次
----------------

这条解决的是一个我之前完全没意识到的问题：长时间的对话里，Claude会开始用上下文里堆积的旧信息来影响后续判断，越聊越偏。

解法是每5-6轮交互后主动问它：

  

`总结一下目前的进展——解决了什么，决定了什么，最重要的未决问题是什么？   `

这相当于给对话清缓存，把它拉回到你真正在问的那个核心问题上。我用在比较长的选题讨论里，发现确实能防止它"自信地解决错误问题"——这是原文里的说法，但描述得挺准。

![3bb6c4bfee289a7de49438ce3677a49a](https://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zmZPmeNfks9zTicBCo7OncsAmHCdANkWv1d67O36WUcOsaCqRTibibXAvSfacKm1TSueAzfJ224bInYgx8icoHtTUoeXFIIo5s0dos/640?wx_fmt=png&from=appmsg)

第10条：上线前做一次预演失败
---------------

最后这条叫"前期验尸"，是10条里我觉得最反直觉的一个。做法是在任何东西上线之前，加这一句：

  

`假设这件事在6个月后失败了，列出3个最可能的原因，要具体，失败的样子是什么？   `

原文说这是Anthropic产品团队每做重大决定都会走的流程，能找到其他审查方式发现不了的问题。就是逼你在事情还没做之前，站在失败那边往回看——自己做这件事很难，因为你已经有滤镜了，但Claude没有，它可以毫无负担地列出你不想承认的那些原因。我试了一个已经打算执行的方案，它给出来的第二条原因让我改了一个关键细节。

![ede9fa6e936af7ca2ad04e64af01c618](https://mmbiz.qpic.cn/sz_mmbiz_png/JYWVQlsu9zmKNv2lic9LWMTC3VtC8IjMbmINKA7ztF4weAttuJjz3fWEVbbBdb0qxzbOgS40kxrX5ualbfRWn98qC3HuT6ayFMYol1zUsEW8/640?wx_fmt=png&from=appmsg)

* * *

10条试完，印象最深的是**第3、5、10条——强制诚实、魔鬼代言人、前期验尸。**这三条其实在干同一件事：Claude默认是配合你的，想帮你、不想惹你不高兴，这三条都是在把那个配合模式掰开，让它说它真正觉得有问题的地方。

剩下几条更偏工程性，像格式命令和范围锁定，知道了直接用就行，没什么好说的。

我把这10条攒成一个常用提示词集，最近一直在轮换着用。如果你也试了，哪条效果最明显，可以评论告诉我。

⭐以上，既然看到这里了，如果觉得不错，随手点个赞、在看、转发三连吧，谢谢你看我的文章，我们下次再见。

[一文详解硅谷爆火的 Harness Engineering](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484984&idx=1&sn=553ee860b67061d9b80e53faea2e47be&scene=21#wechat_redirect)

[这个skill太硬核了！刚开源就狂揽11万Star！让agent像正经工程师一样干活](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484974&idx=1&sn=321f1f83eb298f6351d8fdc75fea3dce&scene=21#wechat_redirect)

[限时白嫖谷歌Gemini pro会员 | 无需Pixel设备，亲测有效！](https://mp.weixin.qq.com/s?__biz=MzkzNjYyNzg4Mw==&mid=2247484969&idx=1&sn=8a658a3c3590e0b6e9a69a9dbf3808bb&scene=21#wechat_redirect)

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言