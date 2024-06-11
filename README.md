# Spreadsheet Is All You Need (Excel version added!)
**A nanoGPT pipeline packed in a spreadsheet**

This is a project that I did to help myself understand how GPT works.<br>
It is pretty fun to play with, especially when you are trying to figure out what exactly is going on inside a transformer.<br>
This helped me to visualize the entire structure and the data flow.<br> 
All the mechanisms, calculations, matrices inside are fully interactive and configurable.<br>

While reading about LLMs, I realised that the internal mechanisms of a transformer is basically a range of matrices calculations being connected in a certain order.<br>
I started to wonder if the whole process can be represented in a spreadsheet since all the calculations are fairly simple.
I'm a visual thinker, I couldn't think of a better way to do it.
Then with some trial and errors, I wrote the full inference pipeline of the nanoGPT architecture into a single spreadsheet.<br>
Forget python, it turned out that <mark>**spreadsheet is all you need**<mark>.


**This is the full view of the spreadsheet**
![**spreadsheet is all you need**](https://github.com/dabochen/spreadsheet-is-all-you-need/blob/main/spreadsheetisallyouneed.jpg?raw=true)

**Zooming into the core of a transformer--self attention**
![**The core of a transformer--self attention**](https://github.com/dabochen/spreadsheet-is-all-you-need/blob/main/KQV.jpg?raw=true)


## What components will you see
It contains all the transformer components including:
1. embedding
2. layer norm
3. self attention
4. projection
5. MLP
6. softmax
7. logits

It is based on Andrej Karpathy's NanoGPT structure which includes roughly 85000 parameters.<br>
It is clearly a very small size, but it is both complex enough for me to understand how it works, and also not too big to crash my computer.
In contrast to chatgpt, this project is a character based prediction system, meaning that each token is a character, and to reduce the complexity, only letter A/B/C are being tokenized.

## What else is included 
In the numbers file "nanoGPT.numbers", you will see two tabs, one called "no weights" and one called "random weights".<br>
They are essentially the same thing, only that all the parameters in the "random weights" tab is randomly generated and the parameters in the "no weights" tab is very tidy and it shows weird values down the pipeline, but it is also clearer to help you read it. That's why I kept both.<br>
Due to the internal mechanism of spreadsheet softwares, everytime you update the spreadsheet in the "random weights" tab, all the values will be regenerated again (freezes the computer for a few seconds as it is a lot of calculation which is a bit annoying, but you can avoid it by turning all the values into a static value).<br>

The spreadsheet doesn't contain actual trained weights and parameters, so you should not expect it to calculate the correct result for you before you update the parameters.

You might also be wondering if there is an excel or a google sheets version, unfortunately there isn't one yet.<br>
It is simply because the whole pipeline is too large and I need multiple tables to organize everything, and only numbers can do this.<br>
I will see if I can recreate this in excel in the near future(It is added now, just check the excel file in the list).

## How to read it/use it
Firstly, all the blocks are the values or parameters that is processed through the GPT architecture, they are being color coded as purple, green and orange.

**Purple**: these are parameters that are supposed be replaced by a trained model's parameter.<br>
**Green**: these are the values that started from the input and gets transformed into the end results.<br>
**Orange**: these are just intermediate values that are used for the calculation, they are here so it is less confusing.

Secondly, you should start from the top and work all the way down to the bottom, and there are labels on the left of the page showing what stage you are in.<br>
There are three transformers labeled 0/1/2, each have the same structure and should contain different parameters, data will go through all of them in the sequential order.

Lastly, this demo is built with great help from the LLM visualization project (https://bbycroft.net/llm) by Brendan Bycroft which uses 3D animations to explain transformers.<br>
I kept the example it used which is about sorting letters.

If you are using the recently added Excel version, you will note that it might look the same as the attached images, this is due to the limitation of excel not being able to include multiple tables on one page, to make it clearer, I added the "MAP" tab and "Visual Structure of the pipeline" tab, these two will give you a menu and a rought layout of the architecture, you can click on the link to jump to the page and come back using the go back link on the top left of each page.

## What else can you do with this
1. Read through the whole spreadsheet will help you form a visual impression of what a transformer is.
2. Each cell contains the actual calculation, which you can double click to checkout the details(function).
3. By selecting the green cells (the values), you can see which other values or parameters are influencing this cell, so that you can get a sense of the mechanism.
4. Try to make changes to the parameters and see what might happen.
5. If you happen to have the weights of NanoGPT, you can replace the parameters in this spreadsheet to get it working properly.


## Contribution
I wish I could just upload all the tutorials I've watched into chatgpt and ask it to generate this file, but I guess we are not there yet.
Anyone is welcomed if they want to build something more complicated than nanoGPT, although I do feel like nanoGPT in a spreadsheet is already a lot for my M2 chip.<br>


## Special Thanks
Thanks to the following projects that helped me a lot when creating this spreasheet.<br>
If you are interested in my project, the following links will also be very helpful, much more helpful than spreadsheet is all you need.

1. [**Andrej Karpathy's youtube tutorial "Let's build GPT"**](https://www.youtube.com/watch?v=kCc8FmEb1nY): https://www.youtube.com/watch?v=kCc8FmEb1nY
2. [**Andrej Karpathy's NanoGPT project**](https://github.com/karpathy/nanoGPT): https://github.com/karpathy/nanoGPT
3. [**Brendan Bycroft's 3D visualization of transformers**](https://bbycroft.net/llm): https://bbycroft.net/llm
4. [**3Blue1Brown's LLM course**](https://youtu.be/eMlx5fFNoYc?si=k40zeuPdM_4cB88o): https://youtu.be/eMlx5fFNoYc?si=k40zeuPdM_4cB88o

# 你只需要电子表格（新增 Excel 版本！）
**一个封装在电子表格中的 nanoGPT 流程**

这是我为了更好地理解 GPT 工作原理而做的一个项目。<br>
特别有趣，尤其是当你尝试弄清楚变换器内部发生了什么时。<br>
这帮助我可视化了整个结构和数据流。<br> 
所有机制、计算和矩阵都是完全互动和可配置的。<br>

在阅读关于大型语言模型（LLM）时，我意识到变换器的内部机制基本上是一系列矩阵计算按照特定顺序连接。<br>
我开始想，是否可以在电子表格中表示整个过程，因为所有计算都相对简单。
作为一个视觉型思考者，我想不出更好的方式了。
经过一些尝试和错误后，我将 nanoGPT 架构的完整推理流程写入了一个电子表格。<br>
忘了 Python，结果证明**你只需要电子表格**。

**电子表格的全视图**
![**你只需要电子表格**](https://github.com/dabochen/spreadsheet-is-all-you-need/blob/main/spreadsheetisallyouneed.jpg?raw=true)

**深入变换器的核心--自注意力**
![**变换器的核心--自注意力**](https://github.com/dabochen/spreadsheet-is-all-you-need/blob/main/KQV.jpg?raw=true)

## 你会看到哪些组件
它包含所有变换器组件，包括：
1. 嵌入
2. 层规范化
3. 自注意力
4. 投影
5. MLP
6. softmax
7. logits

它基于 Andrej Karpathy 的 NanoGPT 结构，包括大约 85000 个参数。<br>
尽管规模很小，但复杂到足以让我理解其工作原理，也不至于让我的计算机崩溃。
与 chatgpt 不同，这个项目是基于字符的预测系统，意味着每个标记都是一个字符，为了减少复杂性，只有 A/B/C 三个字母被标记。

## 还包括什么
在 numbers 文件“nanoGPT.numbers”中，你会看到两个标签页，一个叫做“无权重”，另一个叫做“随机权重”。<br>
它们本质上是一样的，只是“随机权重”标签页中的所有参数都是随机生成的，而“无权重”标签页中的参数非常整洁，它显示了管道中的奇怪值，但也更清晰，以帮助你阅读。这就是我保留两者的原因。<br>
由于电子表格软件的内部机制，每次在“随机权重”标签页更新电子表格时，所有值都将重新生成（计算量大，冻结电脑几秒钟有点烦人，但你可以通过将所有值转换为静态值来避免这种情况）。<br>

电子表格不包含实际的训练权重和参数，因此在你更新参数之前，不应期望它为你计算正确的结果。

你可能还在想是否有 Excel 或 Google 表格版本，遗憾的是目前还没有。<br>
这仅仅是因为整个流程太大了，我需要多个表格来组织一切，只有 numbers 能做到这一点。<br>
我将看看是否可以在不久的将来在 Excel 中重新创建它（现在已添加，只需检查列表中的 Excel 文件）。

## 如何

读取/使用它
首先，所有块都是通过 GPT 架构处理的值或参数，它们被编码为紫色、绿色和橙色。

**紫色**：这些是应由训练有素的模型的参数替换的参数。<br>
**绿色**：这些是从输入开始并转换成最终结果的值。<br>
**橙色**：这些只是用于计算的中间值，放在这里是为了减少混淆。

其次，你应该从顶部开始，一直工作到底部，页面左侧有标签显示你所处的阶段。<br>
有三个变压器标记为 0/1/2，每个都有相同的结构，应包含不同的参数，数据将按顺序通过所有这些变压器。

最后，这个演示得到了 LLM 可视化项目的巨大帮助（https://bbycroft.net/llm）由 Brendan Bycroft 制作，它使用 3D 动画来解释变压器。<br>
我保留了它使用的例子，即关于排序字母的例子。

如果你正在使用最近添加的 Excel 版本，你会注意到它可能看起来与附图相同，这是因为 Excel 的限制，不能在一个页面上包含多个表格，为了更清晰，我添加了“MAP”标签和“管道的视觉结构”标签，这两个标签会提供一个菜单和架构的大致布局，你可以点击链接跳转到页面，并使用页面左上角的返回链接返回。
