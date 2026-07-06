     Manus花了几千万美元学费的经验教训，且看且珍惜！ \* { margin: 0; padding: 0; outline: 0; } body { font-family: "PingFang SC", system-ui, -apple-system, BlinkMacSystemFont, "Helvetica Neue", "Hiragino Sans GB", "Microsoft YaHei UI", "Microsoft YaHei", Arial, sans-serif; line-height: 1.6; } .\_\_page\_content\_\_ { max-width: 667px; margin: 0 auto; padding: 20px; text-size-adjust: 100%; color: rgba(0, 0, 0, 0.9); padding-bottom: 64px; } .title { user-select: text; font-size: 22px; line-height: 1.4; margin-bottom: 14px; font-weight: 500; } .\_\_meta\_\_ { color: rgba(0, 0, 0, 0.3); font-size: 15px; line-height: 20px; hyphens: auto; word-break: break-word; margin-bottom: 50px; } .\_\_meta\_\_ .nick\_name { color: #576B95; } .\_\_meta\_\_ .copyright { color: rgba(0, 0, 0, 0.3); background-color: rgba(0, 0, 0, 0.05); padding: 0 4px; margin: 0 10px 10px 0; } blockquote.source { padding: 10px; margin: 30px 0; border-left: 5px solid #ccc; color: #333; font-style: italic; word-wrap: break-word; } blockquote.source a { cursor: pointer; text-decoration: underline; } .item\_show\_type\_0 > section { margin-top: 0; margin-bottom: 24px; } a { color: #576B95; text-decoration: none; cursor: default; } .text\_content { margin-bottom: 50px; user-select: text; font-size: 17px; white-space: pre-wrap; word-wrap: break-word; line-height: 28px; hyphens: auto; } .picture\_content .picture\_item { margin-bottom: 30px; } .picture\_content .picture\_item .picture\_item\_label { text-align: center; } img { max-width: 100%; } .pay\_subscribe\_notice { margin: 30px 0; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; } .pay\_subscribe\_badge { display: inline-block; padding: 4px 12px; background: #faad14; color: #fff; border-radius: 4px; font-size: 14px; font-weight: 500; margin-bottom: 12px; } .pay\_subscribe\_desc { font-size: 15px; line-height: 1.8; color: rgba(0, 0, 0, 0.7); margin-bottom: 12px; } .pay\_subscribe\_hint { font-size: 13px; color: rgba(0, 0, 0, 0.4); } .\_\_bottom-bar\_\_ { display: flex; justify-content: space-between; align-items: center; position: fixed; bottom: 0; left: 0; right: 0; height: 64px; padding: 8px 20px; background: white; box-sizing: border-box; border-top: 1px solid rgba(0, 0, 0, 0.2); } .\_\_bottom-bar\_\_ .left { display: flex; align-items: center; font-size: 15px; white-space: nowrap; } .\_\_bottom-bar\_\_ .right { display: flex; } .\_\_bottom-bar\_\_ .sns\_opr\_btn { display: flex; align-items: center; user-select: none; background: transparent; border: 0; color: rgba(0, 0, 0, 0.9); font-size: 14px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn:not(:last-child) { margin-right: 16px; } .\_\_bottom-bar\_\_ .sns\_opr\_btn > img { margin-right: 4px; }

Manus花了几千万美元学费的经验教训，且看且珍惜！
==========================

原创 404 AI飞升录 2025-07-19 21:27 浙江

> 原文地址: [https://mp.weixin.qq.com/s/rrLxEMt9MhqbOuSJ8b3u2g](https://mp.weixin.qq.com/s/rrLxEMt9MhqbOuSJ8b3u2g)

这是一篇Manus内部花了几千万美元的实践分享，考虑到很多用户现在无法访问manus所以帮忙将原文贴在这里，仅供学习参考。

![](https://mmbiz.qpic.cn/mmbiz_jpg/FTOSnyk3X7O3wqR4DzpusWvV15nRQzeg10fyEuqDlpZtjqDSCQ3ZJMOtT2yicIF4dDWpK15Vg8nxeeiaVumWPAXw/640?wx_fmt=jpeg&from=appmsg)

在 Manus 项目的最开始，我和我的团队面临了一个关键决策：我们应该使用开源基础来训练一个端到端的代理模型，还是基于前沿模型的上下文学习能力构建一个代理？

在我 NLP 领域的第一个十年里，我们没有那种选择的奢侈。在遥远的 BERT（是的，已经过去了七年）的那些日子里，模型在转移到新任务之前必须进行微调——并进行评估。这个过程每个迭代都要花几周时间，尽管与今天的 LLMs 相比，这些模型非常小。对于快速发展的应用，尤其是 PMF 之前的应用，这种缓慢的反馈循环是致命的。这是我上一家创业公司的一个苦涩教训，在那里我为开放信息提取和语义搜索从头训练模型。 接着出现了 GPT-3 和 Flan-T5，我的内部模型在一夜之间变得无关紧要。讽刺的是，正是这些相同的模型标志着情境学习的开始——以及一条全新的发展道路。

这个来之不易的教训让选择变得清晰： Manus 将押注于情境工程 。这使我们能够在几小时内而不是几周内交付改进，并使我们的产品与底层模型保持正交： 如果模型进步是涨潮，我们希望 Manus 成为船 ，而不是固定在海底的柱子。

然而，上下文工程却远非易事。它是一门实验科学——我们重建了四次智能体框架，每次都是在发现更优的上下文构建方法后。我们亲昵地将这种架构搜索、提示词调试和经验性猜测的过程称为" 随机 梯度下降法 ". 它并不优雅，但有效。

本文分享了我们在自己的"SGD"过程中达到的局部最优解。如果你正在构建自己的 AI 智能体，希望这些原则能助你更快收敛。

### 围绕 KV 缓存进行设计

如果必须选择一个指标，我会认为 KV 缓存命中率是生产阶段 AI 代理最重要的指标。它直接影响延迟和成本。要理解原因，让我们看看典型代理是如何运行的：

在接收到用户输入后，智能体通过一系列工具使用来完成任务。在每次迭代中，模型根据当前上下文从预定义的动作空间中选择一个动作。然后在该动作在环境中执行（例如 Manus 的虚拟机沙盒），以产生一个观察结果。该动作和观察结果被追加到上下文中，形成下一次迭代的输入。这个循环会一直持续到任务完成。

你可以想象，随着每一步的进行，上下文会不断增长，而输出——通常是一个结构化的函数调用——则相对较短。这使得在智能体与聊天机器人之间，预填充与解码之间的比例严重失衡。例如，在 Manus 中，平均输入与输出的 token 比例约为 100:1。

幸运的是，具有相同前缀的上下文可以利用 KV 缓存，这能大幅降低首次获取 token 的时间（TTFT）和推理成本——无论你是使用自托管模型还是调用推理 API。而且我们谈论的不是微小的节省：以 Claude Sonnet 为例，缓存的输入 token 成本为 0.30 美元/百万 token（MTok），而未缓存的成本为 3 美元/MTok——相差 10 倍。

![](https://mmbiz.qpic.cn/mmbiz_png/FTOSnyk3X7O3wqR4DzpusWvV15nRQzeg8us8eKQrlYv69L7siafgzGHA7zp77ic9g39Ow1GMLuVphGltgx8cLyng/640?wx_fmt=png&from=appmsg)

从上下文工程的角度来看，提高 KV 缓存命中率涉及几个关键实践：

1.保持你的提示前缀稳定。 由于 LLMs 的自回归特性，即使是一个 token 的差异也可能使从该 token 开始的所有缓存失效。一个常见的错误是在系统提示的开头包含时间戳——尤其是精确到秒的时间戳。当然，它允许模型告诉你当前时间，但它也会使你的缓存命中率降低。

2.让你的上下文只追加不修改。 避免修改先前的动作或观察结果。确保你的序列化是确定性的。许多编程语言和库在序列化 JSON 对象时不能保证键的稳定顺序，这可能会无声地破坏缓存。

3.需要时明确设置缓存断点。 某些模型提供者或推理框架不支持自动增量前缀缓存，而是需要在上下文中手动插入缓存断点。设置这些断点时，要考虑潜在的缓存过期问题，至少要确保断点包含系统提示的结尾。

此外，如果你使用 vLLM 等框架自托管模型，请确保 前缀/提示缓存已启用，并使用会话 ID 等技术来在分布式工作节点间一致地路由请求。

### 遮蔽，而非移除

随着你的智能体具备更多功能，其行为空间自然会变得更加复杂——用直白的话来说，就是工具的数量呈爆炸式增长。近期 MCP 的流行更是火上浇油。如果你允许用户可配置的工具，我向你保证：总有人会不可避免地将数百个神秘工具接入你精心构建的行为空间。结果，模型更有可能选择错误的行为或采取低效的路径。简而言之，你武装到牙齿的智能体反而变得更笨了。

自然的反应是设计一个动态动作空间——也许通过某种 RAG 类似的技术按需加载工具。我们在 Manus 中也尝试过这种方法。但我们的实验表明有一个明确的规则：除非绝对必要， 避免在迭代过程中动态添加或删除工具 。这主要有两个原因：

1.在大多数 LLMs 中，工具定义在序列化后位于上下文的前部，通常位于系统提示之前或之后。因此，任何更改都会使后续所有操作和观察的 KV 缓存失效。

2.当先前的行为和观察仍然指向当前上下文中不再定义的工具时，模型会感到困惑。如果没有约束解码 ，这种情况通常会导致模式违规或幻觉行为 。

为了解决这个问题同时还能改进动作选择，Manus 使用了一种上下文感知的状态机来管理工具的可用性。它不是移除工具，而是在解码过程中掩盖 token logits，以防止（或强制）根据当前上下文选择某些动作。

![](https://mmbiz.qpic.cn/mmbiz_png/FTOSnyk3X7O3wqR4DzpusWvV15nRQzegyv6dwvCSK7flnJBxXCpnlDw2lKOcs7qqIE2ObA0JDvicppzzwN4garA/640?wx_fmt=png&from=appmsg)

实际上，大多数模型提供程序和推理框架都支持某种形式的响应预填充 ，这允许您在不修改工具定义的情况下限制操作空间 。函数调用通常有三种模式（我们将使用 NousResearch 的 Hermes 格式作为示例）：

•自动 – 模型可以选择调用函数或不调用。通过仅预填充回复前缀实现：<|im\_start|>assistant

•必须 – 模型必须调用函数，但选择不受约束。通过预填充到工具调用标记实现：<|im\_start|>assistant<tool\_call>

•指定 – 模型必须调用一个特定子集中的函数 ：通过在函数名开头预填充实现：  <|im\_start|>assistant<tool\_call>{"name": “browser\_

利用这一点，我们通过直接遮蔽 token logits 来约束动作选择。例如，当用户提供新的输入时，Manus 必须立即回复而不是采取行动。我们还特意设计了具有一致前缀的动作名称——例如，所有与浏览器相关的工具都以 browser\_开头，而命令行工具则以 shell\_开头。这使我们能够轻松地强制代理在特定状态下仅从一组特定的工具中选择，而无需使用状态 logits 处理器。

这些设计有助于确保 Manus 代理循环保持稳定——即使在模型驱动架构下也是如此。

### 使用文件系统作为上下文

现代前沿 LLMs 现在提供 128K 个 token 或更多的上下文窗口。但在实际代理场景中，这通常不够，有时甚至是一个缺点。有三个常见的痛点：

1.观察结果可能很大 ，尤其是在代理与网页或 PDF 等非结构化数据交互时。很容易超出上下文限制。

2.模型性能往往会在某个特定的上下文长度之外下降 ，即使窗口技术上是支持的。

3.长输入仍然很昂贵 ，即使有前缀缓存。你仍然需要支付传输和预填充每个标记的成本。

为了解决这个问题，许多代理系统实现了上下文截断或压缩策略。但过于激进的压缩不可避免地会导致信息丢失。问题是根本性的：代理本质上必须根据所有先前的状态来预测下一步行动——而你无法可靠地预测哪个观察结果可能在十步之后变得关键。从逻辑上讲，任何不可逆的压缩都存在风险。

这就是为什么我们将文件系统视为 Manus 中的终极上下文：容量无限、天生持久，并且可以直接由代理本身操作。模型学会按需写入和读取文件——使用文件系统不仅作为存储，更作为结构化、外化的内存。

![](https://mmbiz.qpic.cn/mmbiz_png/FTOSnyk3X7O3wqR4DzpusWvV15nRQzegbQvc0vuzGOr9oBbPQycjXI34tnic17nqbG6ibaXqD0DLmvM0MuRdIS9A/640?wx_fmt=png&from=appmsg)

我们的压缩策略始终设计为可恢复 。例如，只要保留 URL，网页内容可以从上下文中移除，如果文档路径在沙盒中仍然可用，文档内容也可以被省略。这允许 Manus 在不永久丢失信息的情况下缩短上下文长度。

在开发这个功能时，我发现自己在想象一个状态空间模型（SSM）要在代理环境中有效工作需要什么。与 Transformer 不同，SSM 缺乏完整的注意力机制，并且难以处理长距离的逆向依赖。但如果它们能够掌握基于文件的记忆——将长期状态外部化而不是在上下文中持有——那么它们的速度和效率可能会解锁一类新的代理。代理式 SSM 可能是真正的《神经图灵机》的继承者。Neural Turing Machines.

### 通过吟诵来操控注意力

如果你使用过 Manus，可能注意到一个有趣的现象：在处理复杂任务时，它倾向于创建一个 todo.md 文件——并且随着任务的进展逐步更新它，勾选已完成的项。

这不仅仅是可爱行为——它是一种刻意机制来操纵注意力 .

![](https://mmbiz.qpic.cn/mmbiz_png/FTOSnyk3X7O3wqR4DzpusWvV15nRQzegrAHTO80Lj8BCEibHJ8cQxL6zc9Ro8LFmqvFyDq45yAc6qUqyj2ylGZw/640?wx_fmt=png&from=appmsg)

在 Manus 中，一个典型的任务需要大约 50 次工具调用 。这是一个漫长的循环——由于 Manus 依赖 LLMs 进行决策，它容易偏离主题或忘记早期目标，特别是在长上下文或复杂任务中。

通过不断重写待办事项列表，Manus 将其目标重述到上下文的末尾 。这使全局计划进入模型的近期注意力范围，避免了" 中间丢失 "问题，并减少了目标错位。实际上，它正在使用自然语言来使其自身注意力偏向任务目标——而无需进行特殊的架构变更。

### 保留错误信息

智能体可能会犯错。这不是一个 bug——这是现实。语言模型会胡言乱语，环境会返回错误，外部工具会表现异常，而意想不到的边缘情况总是出现。在多步骤任务中，失败不是例外；它是循环的一部分。

然而，一个常见的冲动是隐藏这些错误：清理痕迹，重试操作，或重置模型状态，然后将其交给神奇的“ 温度 ”。这感觉更安全，更可控。但它是有代价的： 抹去失败会消除证据 。而没有证据，模型就无法适应。

![](https://mmbiz.qpic.cn/mmbiz_png/FTOSnyk3X7O3wqR4DzpusWvV15nRQzegjNfkKIKLCbksWS59RpzqAnFhX3ceX3NyvC6YBv4Vic1VyOaGeEsiaT5A/640?wx_fmt=png&from=appmsg)

根据我们的经验，改进智能体行为最有效的方法之一出奇地简单： 在上下文中保留错误的操作 。当模型看到一个失败的行动——以及由此产生的观察结果或堆栈跟踪——它会隐式地更新其内部信念。这使其先验概率偏离相似行动，从而降低重复相同错误的可能性。 事实上，我们相信错误恢复是真正智能体行为的明显指标。然而，它仍然在大多数学术研究和公开基准中代表性不足，这些基准往往专注于理想条件下的任务成功。

### 不要被少数样本击倒

少样本提示是一种常见的改进 LLM 输出的技术。但在智能体系统中，它可能以微妙的方式适得其反。

语言模型是出色的模仿者；它们模仿上下文中的行为模式 。如果你的上下文中充满了相似的过去行动-观察对，模型会倾向于遵循该模式，即使它不再是最优的。

这在涉及重复决策或行动的任务中可能很危险。例如，当使用 Manus 来帮助审阅一批 20 份简历时，智能体常常陷入一种节奏——仅仅因为上下文中看到的行为而重复相似的行动。这会导致漂移、过度泛化，有时甚至产生幻觉。

![](https://mmbiz.qpic.cn/mmbiz_png/FTOSnyk3X7O3wqR4DzpusWvV15nRQzegMPWQfxOMIJB0oEuvWthicFt5hictuuKCicTUwI7JyJv6dA4LrTfrAdl1Q/640?wx_fmt=png&from=appmsg)

解决方法是增加多样性 。Manus 在行为和观察中引入了少量的结构化变化——不同的序列化模板、替代性措辞、顺序或格式中的轻微噪声。这种可控的随机性有助于打破模式并调整模型的注意力。 换句话说， 不要让自己陷入少数样本的困境 。你的上下文越统一，你的智能体就越脆弱。

### 结论

上下文工程仍然是一门新兴的科学——但对于智能体系统来说，它已经至关重要。模型可能越来越强大、快速且便宜，但无论原始能力有多大，都无法替代记忆、环境和反馈的需求。你如何塑造上下文最终决定了你的智能体的行为：它运行的速度、恢复的能力以及扩展的范围。

在 Manus，我们通过反复重写、走死胡同以及数百万用户的实际测试中学到了这些教训 。我们在这里分享的任何内容都不是普遍真理——但这些是我们行之有效的模式。如果它们能帮助您避免一次痛苦的迭代，那么这篇帖子就完成了它的任务。

智能体的未来将是一次次通过上下文构建起来的。把上下文工程好。

### \-END-

参考文献：Yichao 'Peak' Ji《AI 代理的上下文工程：从构建 Manus 项目中的经验教训》（2025-07-18）

原文链接和源文件我都打包到公众号里了 有需要的小伙伴回复`Manus`自取即可，有收获的话可以分享给身边有需要的人。

![](http://mmbiz.qpic.cn/mmbiz_png/JYWVQlsu9zlF8zFXeqebcaibib9NT0KeTr2DoIEcmTzLZ4H3Joa7aiaLrbicuVAlI1MEjiaWe12HMJe6qroo2UPia7XSuCia2IaQyjoLhBrzsWIqLM/0?wx_fmt=png) AI飞升录

 ![](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3C!-- Icon from Lucide by Lucide Contributors - https://github.com/lucide-icons/lucide/blob/main/LICENSE --%3E%3Cg fill='none' stroke='%23888888' stroke-linecap='round' stroke-linejoin='round' stroke-width='2'%3E%3Cpath d='M2.062 12.348a1 1 0 0 1 0-.696a10.75 10.75 0 0 1 19.876 0a1 1 0 0 1 0 .696a10.75 10.75 0 0 1-19.876 0'/%3E%3Ccircle cx='12' cy='12' r='3'/%3E%3C/g%3E%3C/svg%3E) 阅读![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M16.154 6.797l-.177 2.758h4.009c1.346 0 2.359 1.385 2.155 2.763l-.026.148-1.429 6.743c-.212.993-1.02 1.713-1.977 1.783l-.152.006-13.707-.006c-.553 0-1-.448-1-1v-8.58a1 1 0 0 1 1-1h2.44l1.263-.03.417-.018.168-.015.028-.005c1.355-.315 2.39-2.406 2.58-4.276l.01-.16.022-.572.022-.276c.074-.707.3-1.54 1.08-1.883 2.054-.9 3.387 1.835 3.274 3.62zm-2.791-2.52c-.16.07-.282.294-.345.713l-.022.167-.019.224-.023.604-.014.204c-.253 2.486-1.615 4.885-3.502 5.324l-.097.018-.204.023-.181.012-.256.01v8.218l9.813.004.11-.003c.381-.028.72-.304.855-.709l.034-.125 1.422-6.708.02-.11c.099-.668-.354-1.308-.87-1.381l-.098-.007h-5.289l.26-4.033c.09-1.449-.864-2.766-1.594-2.446zM7.5 11.606l-.21.005-2.241-.001v8.181l2.45.001v-8.186z' fill='%23000'/%3E%3C/svg%3E) 赞 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cpath d='M0 0h24v24H0z'/%3E    %3Cpath fill='%23576B95' d='M13.707 3.288l7.171 7.103a1 1 0 0 1 .09 1.32l-.09.1-7.17 7.104a1 1 0 0 1-1.705-.71v-3.283c-2.338.188-5.752 1.57-7.527 5.9-.295.72-1.02.713-1.177-.22-1.246-7.38 2.952-12.387 8.704-13.294v-3.31a1 1 0 0 1 1.704-.71zm-.504 5.046l-1.013.16c-4.825.76-7.976 4.52-7.907 9.759l.007.287c1.594-2.613 4.268-4.45 7.332-4.787l1.581-.132v4.103l6.688-6.623-6.688-6.623v3.856z'/%3E  %3C/g%3E%3C/svg%3E) 分享 ![](data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='24' height='24' viewBox='0 0 24 24'%3E  %3Cdefs%3E    %3Cpath id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-a' d='M0 0h24v24H0z'/%3E  %3C/defs%3E  %3Cg fill='none' fill-rule='evenodd'%3E    %3Cmask id='a62bde5b-af55-42c8-87f2-e10e8a48baa0-b' fill='%23fff'%3E      %3Cuse xlink:href='%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-a'/%3E    %3C/mask%3E    %3Cg mask='url(%23a62bde5b-af55-42c8-87f2-e10e8a48baa0-b)'%3E      %3Cg transform='translate(0 -2.349)'%3E        %3Cpath d='M0 2.349h24v24H0z'/%3E        %3Cpath fill='%23576B95' d='M16.45 7.68c-.954 0-1.94.362-2.77 1.113l-1.676 1.676-1.853-1.838a3.787 3.787 0 0 0-2.63-.971 3.785 3.785 0 0 0-2.596 1.112 3.786 3.786 0 0 0-1.113 2.687c0 .97.368 1.938 1.105 2.679l7.082 6.527 7.226-6.678a3.787 3.787 0 0 0 .962-2.618 3.785 3.785 0 0 0-1.112-2.597A3.687 3.687 0 0 0 16.45 7.68zm3.473.243a4.985 4.985 0 0 1 1.464 3.418 4.98 4.98 0 0 1-1.29 3.47l-.017.02-7.47 6.903a.9.9 0 0 1-1.22 0l-7.305-6.73-.008-.01a4.986 4.986 0 0 1-1.465-3.535c0-1.279.488-2.56 1.465-3.536A4.985 4.985 0 0 1 7.494 6.46c1.24-.029 2.49.4 3.472 1.29l.01.01L12 8.774l.851-.85.01-.01c1.046-.951 2.322-1.434 3.59-1.434 1.273 0 2.52.49 3.472 1.442z'/%3E      %3C/g%3E    %3C/g%3E  %3C/g%3E%3C/svg%3E) 推荐 ![](data:image/svg+xml,%3Csvg width='25' height='24' viewBox='0 0 25 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M22.242 7a2.5 2.5 0 0 0-2.5-2.5h-14a2.5 2.5 0 0 0-2.5 2.5v8.5a2.5 2.5 0 0 0 2.5 2.5h2.5v1.59a1 1 0 0 0 1.707.7l1-1a.569.569 0 0 0 .034-.03l1.273-1.273a.6.6 0 0 0-.8-.892v-.006L9.441 19.1l.001-2.3h-3.7l-.133-.007A1.3 1.3 0 0 1 4.442 15.5V7l.007-.133A1.3 1.3 0 0 1 5.742 5.7h14l.133.007A1.3 1.3 0 0 1 21.042 7v4.887a.6.6 0 1 0 1.2 0V7z' fill='%23000' fill-opacity='.9'/%3E%3Crect x='14.625' y='16.686' width='7' height='1.2' rx='.6' fill='%23000' fill-opacity='.9'/%3E%3Crect x='18.725' y='13.786' width='7' height='1.2' rx='.6' transform='rotate(90 18.725 13.786)' fill='%23000' fill-opacity='.9'/%3E%3C/svg%3E) 留言