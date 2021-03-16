# 第二版前言 {.unnumbered}  

欢迎阅读第二版的《ggplot2:数据分析与图形艺术》。我很高兴能有这样一本书，展示ggplot2最新和最强大的功能，以及过去五年在R和ggplot2社区中发生的伟大事情。ggplot2社区充满活力：ggplot2的邮件列表有7,000多个成员，并且有一个非常活跃的Stack Overflow社区，其中有将近10,000个用ggplot2标记的问题。尽管我的大部分开发工作都不再花在ggplot2上了（以下更多内容），但再没有比这更好的时间来学习和使用它了。  

我非常感谢ggplot2的成功。它是最常下载的R软件包之一（去年下载量超过一百万！），并影响了其他语言的图形软件包的设计。就我个人而言，ggplot2为我提供了许多激动人心机会让我环游世界，认识有趣的人。我喜欢听到人们如何使用R和ggplot2来理解他们关心的数据。  

非常感谢Carson Sievert，他帮助我实现了代码的现代化，包括将源代码转换为R Markdown。 他还更新了许多示例，并帮助我对本书进行了校对。  

## 重大改变 {-}  

我已经花了很多心血以确保此版本是对第一个版本的真正升级。除了更新代码以确保与最新版本的ggplot2完全兼容外，我还进行了以下升级：  

+ 本书中显示了更多代码，因此它更容易用作参考。总体而言，这本书更具“编织”感：浮动图形和表格更少，内联代码更多。 这使布局不太美观，但使相关项目更加紧密的联系在一起。  

+ 在github上发布了完整的源代码：https://github.com/hadley/ggplot2-book  

+ 在介绍中将`qplot()`转换为`ggplot()`。反馈表明`qplot()`更像是是一把拐杖：它使简单的绘图变得更容易，但对掌握语法没有帮助。  

+ 在整本书中增加了练习训练，因此您可以在学习新技能后立即进行练习。  

+ 添加了指向围绕ggplot2构建的软件包丰富生态系统的链接。现在，您会看到本书中突出显示了许多其他软件包，并获得了指向我认为特别有用的其他软件包的网络链接。  

+ 全面修订了*Toolbox*一章，以涵盖所有新的图层。我添加了一个全新的部分，因为它很重要，并且在其他地方都没有被详细介绍。映射部分已进行了相当大的扩展，以更多地讨论不同类型的数据以及如何获取他们。  

+ 完全重写了*sacles*一章，将重点放在最重要的任务上。它还讨论了如何更好地控制图例外观的新功能，并展示了添加到ggplot2中的一些标度。  

+ 将数据分析章节分为三部分：数据整理（使用tidyr），数据处理（使用dplyr）和模型可视化（使用broom）。 我讨论了我的数据处理工具的最新版本，并介绍了David Robinson出色的broom软件包。  

本书伴随发布的ggplot2新版本：2.0.0。这包括一些小的调整和改进，以及对文档的相当大的改进。经过相当长的停顿后再回到ggplot2开发，这帮助我看到了许多以前没有引起注意的问题。 ggplot2 2.0.0包含一个官方扩展机制，以便其他人可以在其自己的程序包中提供新的ggplot2组件。这在新的小插图`vignette("extending-ggplot2")`中进行了说明。  

## 展望 {-}  

ggplot2现在很稳定，并且将来不太可能发生很大变化。将来会修复一些错误，并且可能也会产生新的问题，但是ggplot2的工作方式不会有太大变化。ggplot2的下一个迭代产品是ggvis。ggvis更加雄心勃勃，它旨在提供交互式图形语法。 ggvis仍然很年轻，并且缺少ggplot2的许多功能（最需要提醒的是它目前缺乏分面功能，并且无法绘制静态图形），但是在未来几年中，我们的目标是使ggvis优于ggplot2。  

ggvis的语法与ggplot2略有不同。您将无法将ggplot2图转换为ggvis，但我们认为这样是值得的：新语法会更加一致，并且对新手来说更容易学习。如果您精通ggplot2，就会发现在语法上挣扎一段时间后可以非常好的切换到ggvis上，并且开始变得很自然。 掌握ggplot2时，您学习的重要技能不是在代码中描述绘图的编程细节，而是思考如何将数据转换为有效的可视化内容。  

## 致谢 {-}  

许多人通过高层次的结构框架梳理，拼写和语法更正以及错误报告为本书做出了贡献。我要特别感谢William E. J. Doane，Alexander Forrence，Devin Pastoor，David Robinson和Guangchuang Yu对这本书的详细技术评论。 

在ggplot2的生命中（现在已经相当长了）还有其他人做出了许多的贡献。我要感谢：Leland Wilkinson为巩固我对于图形语法的理解而进行的讨论和评论；Gabor Grothendieck提供了早期有用的评论；Heike Hofmann和Di Cook在我的博士期间担任顾问并支持ggplot2的开发；Charlotte Wickham、ISU的 stat480和stat503，在很早期就进行了尝试；Debby Swayne提供了大量有用的反馈和建议；Bob Muenchen、Reinhold Kliegl、Philipp Pagel、Richard Stahlhut、Baptiste Auguie、Jean-Olivier Irisson、Thierry Onkelinx以及其他许多阅读本书草稿并给我反馈的人；最重要的是R-help和ggplot2邮件列表的成员，它们提供了许多有趣且富挑战性的图形问题，这些问题都促使了本书的发展。  

\BeginKnitrBlock{flushright}<p class="flushright">Hadley Wickham  
September 2015</p>\EndKnitrBlock{flushright}

