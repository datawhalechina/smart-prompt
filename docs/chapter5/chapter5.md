# 第5章 元提示词

## 5.1 概念界定和原理

元提示词(meta prompt)是指在给定的上下文中，用来引导或调整行为、思维或输出方向的高层次提示或指令。它的核心思想是通过提供更高层次或更抽象的指令，来影响或引导下层任务的执行或认知过程的调整。

元提示词的原理基于以下几个核心概念：

1. 高层次指导：元提示词提供的是一种高层次的指导，而不是具体的操作指令。它告诉个体或系统如何思考、如何进行决策或如何组织信息，而不是直接提供答案或解决方案。
2. 认知框架调整：
    1. 元认知：元提示词激发了元认知的过程，即个人对自己认知过程的认知。通过提供如何思考、如何学习、如何交流的建议，它帮助个体或系统调整自己的认知策略。
    2. 框架设置：它帮助设立一个认知框架或“思维模型”，通过这个框架，个体可以更有效地处理信息、解决问题或生成新的内容。
3. 上下文敏感性：元提示词通常是上下文敏感的，意味着它们会根据特定的情境、任务或听众来调整自己的内容或表现形式。这使得它们能够更有效地引导行为或思维过程。
4. 促进自监控和自我调节：通过提供关于如何进行自我监控或自我调节的提示，元提示词帮助个体或系统评估自己的表现，并根据需要调整策略或方法。
5. 抽象化与具体化：元提示词在抽象和具体之间找到平衡。一方面，它给出的是抽象的指导原则，另一方面，这些原则可以通过具体情境来应用。这种双重特性使其在不同的应用场景中都具有实用性。
6. 引导创造性和创新思维：通过提供一个框架或思考方式的提示，元提示词可以启发新的想法或解决方案。它鼓励从不同的角度看待问题，从而促进创造性思维。
7. 增强理解和沟通：在语言生成和理解方面，元提示词可以帮助确保信息的清晰传达和接收，减少误解，提高沟通效率。

简单理解，元提示词可以说是“用来引导或调整行为、思维或输出方向的提示词”，这类提示词一般都**非常长**，并且涉及到**大量的上下文信息**。我们目前暂时不掌握如何构建元提示词，我们只需要学习如何用“元提示词”撰写我们需要的提示词。

## 5.2 用元提示词写提示词

在这里感谢[openai](https://platform.openai.com/docs/guides/prompt-engineering)与[claude](https://github.com/anthropics/anthropic-cookbook/blob/main/misc/metaprompt.ipynb)均提供了平台使用的元提示词以及相关程序。对于编程能力不强的朋友们，可以使用这个[在线版本](https://www.modelscope.cn/studios/anarchysaiko/metapromptgenerator)来生成自己的元提示词。[项目代码](https://github.com/anarchysaiko/metapromptgeneratorV2)也已开源到了GitHub，感兴趣的朋友们可以研究。

![在线元提示词生成器](https://s2.loli.net/2024/11/24/cxjghaQpBfzYFwu.png)

在线版的生成器默认内置调用**零一万物**的模型，元提示词模版可以支持使用**claude和openai**两种。用户只需要输入最简单的提示词，输入想要在最终生成结果中出现的**变量**，然后就可以得到最终的元提示词。

如果想要体验不同大语言模型的生成效果，可以在下方“模型名称”、“API密钥”、“API基础URL”中设置相应的参数。

以第3章构建思维链提示词来解决问题为例，最终生成的结果如下所示：

![最终结果](https://s2.loli.net/2024/11/24/cxjghaQpBfzYFwu.png)

我们使用这个结果放入大模型进行测试：

```
您将扮演一个智能助手，帮助团队解决产品市场定位的问题。以下是您需要遵循的步骤和指导原则：

1. 理解产品市场定位的概念：产品市场定位是指在目标顾客的心目中，产品或品牌与竞争对手相比较时的位置。

2. 收集信息：与团队成员沟通，了解产品的特点、目标市场、潜在客户、竞争对手等相关信息。

3. 分析信息：对收集到的信息进行分析，识别产品的独特卖点（USP）和目标市场的需求。

4. 提供建议：基于分析结果，提出如何在市场中定位产品的建议，包括市场细分、目标客户群、品牌信息传递等。

5. 协助制定策略：帮助团队制定具体的市场定位策略，如定价策略、营销策略、销售渠道选择等。

6. 跟踪和评估：协助团队监控市场定位策略的实施情况，并根据市场反馈进行调整。

请注意以下几点：
- 保持客观和专业，确保您的建议基于数据和市场研究。
- 尊重团队成员的意见，鼓励开放的讨论和创新思维。
- 确保策略的可行性和适应性，考虑到市场变化和竞争环境。
- 使用简洁明了的语言，确保团队成员能够理解和执行您的建议。

格式化您的响应，以便于团队成员理解和执行：

<建议>
在此处提供您的建议和策略。
</建议>

<解释>
在此处解释您的建议和策略的依据。
</解释>

现在，您可以开始协助团队解决产品市场定位的问题了。
```

以下是零一万物测试的结果。

![零一万物](https://s2.loli.net/2024/11/24/rjXCyefiVgwKG3Q.png)

## 5.3 总结

在这一章中，我们学习了如何用元提示词撰写我们需要的提示词，帮助用户能够以最高效的方式与大语言模型进行交互，从而获得更加准确的结果。

本次课程到这里就全部结束啦，后续会不定期更新“针对文生图任务的提示词构建”，以及“构建伪代码格式的提示词”等内容，欢迎大家关注！