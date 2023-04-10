# 2023CCL评测：中小学作文流畅度评价(Chinese Essay Fluency Evaluation)

# 最新消息

| 时间 | 消息 |
| --- | --- |
| 4月10日 | [评测任务报名](https://docs.qq.com/form/page/DQkxvUXJLWmVQbGhO) |
|  |  |

# 0 组织者与联系人

&emsp;&emsp;任务组织者：沈新舒（华东师范大学，计算机科学与技术学院），伍洪意（华东师范大学，计算机科学与技术学院），柏晓鹏（华东师范大学，中国语言文学系），兰曼（华东师范大学， 计算机科学与技术学院），吴苑斌（华东师范大学， 计算机科学与技术学院），毛绍光（微软亚洲研究院），葛涛（微软亚洲研究院），夏炎（微软亚洲研究院）

&emsp;&emsp;任务联系人：沈新舒（华东师范大学，shenxinshu11@163.com）

# 1 任务内容

&emsp;&emsp;随着教育的发展和网络的普及，作文评价的规模越来越大，人工评改作文的成本和效率成为一大难题。为了解决这一问题，许多研究者和机构开始探索利用计算机技术来实现作文的自动评改[1]，通过分析作文的语言、内容、结构等方面的特点及存在的问题，给出客观、准确、及时的评分和反馈。其中，表述是否流畅是教师评改作文的一项重要内容。

&emsp;&emsp;作文流畅性反映一篇作文的通顺程度和语言使用的规范性，以及作者的写作水平和表达能力[2]，对提高作文评改质量、提升作者写作水平具有重要意义。目前，针对作文流畅性评价的研究工作通常从句子长度、词汇复杂度、句子结构等语言学特征角度进行评分或评级[2][3][4][5]；或是作为语法纠错任务，对句子中出现的拼写错误或语法错误进行识别和纠正[3][4]；或是视为病句判断任务[6]，判断一条句子是否是病句；这些方法通常将作文流畅性评价作为一个单独的自然语言处理任务，缺乏多层次、多角度的系统性整合；在对语法错误类型的定义上，以往的工作研究了赘余、缺失、误用、乱序四个粗粒度类别，缺乏更细粒度的错误类型定义；同时，他们的方法不具备良好的可解释性，没有定义作文流畅性评价的细粒度分项，无法对中小学生错误修改给出针对性的指导和修改意见。

&emsp;&emsp;本次评测数据集来源于以汉语为母语的中小学生考试作文，区别于使用基于规则生成或汉语学习者的中介语数据中的错误[7]，以及其他类型母语者的口语、书面语的语法错误，中小学生作文中出现的错误类型更丰富，涉及的语法知识更复杂。因此我们的任务研究中小学生考试作文中的语法错误识别与纠正问题，系统地定义了影响作文流畅性的细粒度错误类型，并给出了修正建议，这种细粒度错误类型的定义与识别能够帮助学生更清楚地了解自己的写作问题，而修正建议能帮助学生更好地修改自己的作文，同时帮助教师更便捷地了解学生写作水平，有助于教师更好地指导学生写作。

&emsp;&emsp;基于此，本次评测任务从词法、句法、语义等多角度对作文流畅性进行详细分析，并给出修改建议，包括：

&emsp;&emsp;&emsp;&emsp;1、中小学作文病句类型识别；

&emsp;&emsp;&emsp;&emsp;2、中小学作文字符级错误识别与纠正；

&emsp;&emsp;&emsp;&emsp;3、中小学作文病句重写；

&emsp;&emsp;共3个赛道，为中小学作文流畅性评改提供更多依据，提供更高质量的作文流畅性评价。

## 1.1 赛道1：中小学作文病句类型识别

- 任务描述：

&emsp;&emsp;由于中小学生写作能力有限，在作文写作时不可避免地会出现词法、句法上的病句，比如句子过长或过短，没有合理的停顿，或者使用了不恰当的词汇和语法。因此识别作文中的病句对学生发现自己错误、提升自己写作水平具有重要意义，也是作文流畅性评价、作文评改的一项重要指标。与出现在语文考试中的病句不同，本次评测中涉及的作文中的病句主要是指在词法、句法上有毛病的句子，病句的存在会降低文章的可读性和表达力，影响文章的质量和效果。以往针对病句的研究将病句识别定义为二分类任务[6]，即判断一个句子是否是病句。然而病句存在多种类型，不同错误类型能够反映作者存在不同的写作问题，以往的做法并不能具体指出作者所犯的错误，也无法帮助作者修改作文和提升作者的写作水平。本次评测从字符级错误和成分级错误两大角度出发，定义了字符级错误、成分残缺型错误、成分赘余型错误、成分搭配不当型错误4类粗粒度错误类型，以及缺字漏字、错别字错误、缺少标点、错用标点、主语不明、谓语残缺、宾语残缺、其他成分残缺、主语多余、虚词多余、其他成分多余、语序不当、动宾搭配不当、其他搭配不当等14种细粒度错误类型，对中小学作文中出现的病句类型进行研究。

- 任务定义：

&emsp;&emsp;中小学作文病句类型识别是一个多标签分类问题，预测一条句子是哪些类型的病句。病句类型标签同时包含词法、句法、语义错误，本次评测任务共定义4个粗粒度错误类型和14个细粒度错误类型。病句类别定义及示例如下表1：

![表1 中小学作文病句类型识别赛道病句类型](https://github.com/paopaobubbletang/test/blob/main/%E8%A1%A81%E4%B8%AD%E5%B0%8F%E5%AD%A6%E4%BD%9C%E6%96%87%E7%97%85%E5%8F%A5%E7%B1%BB%E5%9E%8B%E8%AF%86%E5%88%AB%E8%B5%9B%E9%81%93%E7%97%85%E5%8F%A5%E7%B1%BB%E5%9E%8B.png#{height="50%";width="50%";})
<p align="center">表1 中小学作文病句类型识别赛道病句类型</p>

## 1.2 赛道2：中小学作文字符级错误识别与纠正

- 任务描述：

&emsp;&emsp;中小学作文字符级错误识别与纠正任务旨在自动检测并修改作文中的标点、错别字、缺字漏字等错误，能够反映作者语言使用的规范性，是自然语言处理领域的一项重要任务，也是作文流畅性评价的一项重要工作。以往的文本错误识别与纠错任务数据集通常是基于规则生成的伪数据，或是外国语言学者撰写的文本[7]，对于以中文为母语的用户来说缺乏准确性。因此，一个来源于实际场景，并从更多方面整合影响作文流畅性基本因素的字符级错误识别与纠正任务具有重要研究意义。本次评测任务从缺字漏字、错别字错误、缺少标点、错用标点四个角度研究中小学作文字符级错误的识别与纠正问题。

- 任务定义：

&emsp;&emsp;中小学作文字符级错误主要聚焦于四个方面：缺字漏字、错别字错误、缺少标点、错用标点，字符级错误类别识别任务为多标签分类任务。字符级错误识别与纠正以作文句子作为输入，输出错误类别和修改方式三元组，三元组内容包含所在原句位置、要执行的操作（A-增加，R-替换，D-删除）、及对应位置修改结果；错误类别定义及示例如下表2所示：

![表2 中小学作文字符级错误识别与纠正赛道错误类型](https://github.com/paopaobubbletang/test/blob/main/%E8%A1%A82%E4%B8%AD%E5%B0%8F%E5%AD%A6%E4%BD%9C%E6%96%87%E5%AD%97%E7%AC%A6%E7%BA%A7%E9%94%99%E8%AF%AF%E8%AF%86%E5%88%AB%E4%B8%8E%E7%BA%A0%E6%AD%A3%E8%B5%9B%E9%81%93%E9%94%99%E8%AF%AF%E7%B1%BB%E5%9E%8B.png#{height="50%";width="50%";})
<p align="center">表2 中小学作文字符级错误识别与纠正赛道错误类型</p>

## 1.3 赛道3：中小学作文病句改写

- 任务描述：

&emsp;&emsp;中小学作文病句改写任务是为中小学生作文中出现的错误句子，在保持语义不变的前提下，提供最小化修改方案。以往的工作只是对错误句子类型进行判断，作者只能获取到哪条句子出现了哪种错误，并不知道该如何修改，尤其对于中小学生，本身写作水平有限，写作知识的匮乏，可能并不能从错误句子类型入手自己做出正确的修改。因此，对错误句子进行自动修正对作者了解写作问题、提升写作水平具有重要意义，同时能大大节省教师评改作文时间，提高教师作文批改效率。由于语言的多样性和复杂性，错误句子修改标注本身也是一个比较费时费力的工作，考虑到大规模预训练语言模型的强大效果，所以我们希望获取针对错误句子的多样化修改方案。

- 任务定义：

&emsp;&emsp;中小学作文病句改写任务是一个文本生成任务，输入错误句子，输出修改后的句子。

