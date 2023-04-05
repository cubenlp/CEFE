# 中小学作文流畅度评价(Chinese Essay Fluency Evaluation)评测 2023

## 1 任务内容

随着教育的发展和网络的普及，作文评价的规模越来越大，人工评改作文的成本和效率成为一大难题。为了解决这一问题，许多研究者和机构开始探索利用计算机技术来实现作文的自动评改[1]，通过分析作文的语言、内容、结构等方面的特点及存在的问题，给出客观、准确、及时的评分和反馈。其中，表述是否流畅是教师评改作文的一项重要内容。
作文流畅性反映一篇作文的通顺程度和语言使用的规范性，以及作者的写作水平和表达能力[2]，对提高作文评改质量、提升作者写作水平具有重要意义。目前，针对作文流畅性评价的研究工作通常从句子长度、词汇复杂度、句子结构等语言学特征角度进行评分或评级[2][3][4][5]；或是作为语法纠错任务，对句子中出现的拼写错误或语法错误进行识别和纠正[3][4]；或是视为病句判断任务[6]，判断一条句子是否是病句；这些方法通常将作文流畅性评价作为一个单独的自然语言处理任务，缺乏多层次、多角度的系统性整合；在对语法错误类型的定义上，以往的工作研究了赘余、缺失、误用、乱序四个粗粒度类别，缺乏更细粒度的错误类型定义；同时，他们的方法不具备良好的可解释性，没有定义作文流畅性评价的细粒度分项，无法对中小学生错误修改给出针对性的指导和修改意见。
本次评测数据集来源于以汉语为母语的中小学生考试作文，区别于使用基于规则生成或汉语学习者的中介语数据中的错误[7]，以及其他类型母语者的口语、书面语的语法错误，中小学生作文中出现的错误类型更丰富，涉及的语法知识更复杂。因此我们的任务研究中小学生考试作文中的语法错误识别与纠正问题，系统地定义了影响作文流畅性的细粒度错误类型，并给出了修正建议，这种细粒度错误类型的定义与识别能够帮助学生更清楚地了解自己的写作问题，而修正建议能帮助学生更好地修改自己的作文，同时帮助教师更便捷地了解学生写作水平，有助于教师更好地指导学生写作。
基于此，本次评测任务从词法、句法、语义等多角度对作文流畅性进行详细分析，并给出修改建议，包括：

  1、中小学作文病句类型识别；
  
  2、中小学作文字符级错误识别与纠正；
  
  3、中小学作文病句重写；
  
共3个赛道，为中小学作文流畅性评改提供更多依据，提供更高质量的作文流畅性评价。


\###任务链接待公布
