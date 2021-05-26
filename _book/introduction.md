

\makeatletter

# (PART) 开始 {.unnumbered}  

# 引入 {#introduction}  

## 欢迎来到 ggplot2  

ggplot2是一个生成统计、数据、图形的R包。与大多数其他绘图包不同，ggplot2具有基于基于图形语法的基础绘图语句[@wilkinson:2006]；这允许您通过组合独立的图形组分来构成图形。这一语法设计使得ggplot2非常强大。您可以创建适合特定问题的新的图形，而不仅是仅限于预先定义的图形模式。虽然必须学习一定的语法感觉会很累，但是ggplot2相当容易学习：它有一套简单的核心法则，并且很少有特殊情况的出现。最难的可能是您需要一点时间忘记使用其他绘图工具带来的所有刻板印象和先入之见。  

ggplot2可以提供漂亮简洁的图形，并且可以对诸如图例等细节进行处理。实际上，通过精心调节默认的设置参数可以使您在几秒钟内制作出具有出版质量的图形。 但是，如果您确实有特殊的格式要求，ggplot2全面的主题系统可以使您轻松完成所需的工作。这意味着您不必浪费时间打磨图形使它看起来更漂亮，而是专注于创建最能揭示数据中信息的图表样式。  

ggplot2被设计为可以逐层迭代的工作方式。从显示原始数据的图层开始。然后添加注释和统计摘要图层。这使得你可以用设计分析时使用的相同的结构化思维来生成图形。拉近了脑海中图形样式与绘制出来的图形之间的距离。这对于那些尚未具有结构化分析方案的学生来说是非常有帮助的。

学习语法不仅可以帮助你创建熟悉的图形，还可以帮助你创建更新更好的图形。没有语法，就没有根本的理论，所以大多数图形包只是一个特殊情况的大集合。例如，在base R中，如果你设计了一个新图形，它是由线和点等原始情节元素组成的，所以很难设计与现有情节相结合的新组件。在ggplot2中，用于创建新图形的表达式由更高级的元素组成，如原始数据和统计转换的表示，这些元素可以很容易地与新数据集和其他图组合在一起。  

这本书提供了对ggplot2的实际应用介绍，并提供了大量的示例代码和图形。它还解释了ggplot2所基于的语法。与其他正式系统一样，即使您不了解底层模型，ggplot2也很有用。但是，您对它了解得越多，就越能够更有效地使用ggplot2。  

假如你是一个不熟悉语法的新手，这本书将会教你基础的知识，让你可以重新创建你已经熟悉的情节；向你展示如何使用语法创建新的图形;并最终使您成为能够构建新组件来扩展语法的专家。  

## 什么是图形的语法？  

Wilkinson创建了图形语法用来描述所有统计图形背后的基本特性。图形的语法是对什么是统计图形这一问题的回答。ggplot2[@wickham:2007d]搭建在Wilkinson语法的基础之上，将重点放在重要的图层上，并对其进行调整，以便在R中使用。简而言之，语法告诉我们怎样将数据映射到图形的几何对象(点、线、条)和美学属性(颜色、形状、大小)上。图形还可以包括关于该图坐标系统的数据和信息的统计转换。分面可用于数据中不同子集的绘制。这些独立组件的组合构成了一个完整的图形。  

随着本书的进展，将对基本的语法进行详细的说明。第一个描述的部分说明如下。它介绍了将在本书中使用的一些术语，并概述了每个组件的基本功能。不用担心不能理解它们的具体含义：您会有更多的机会了解这些组件以及它们如何协同工作。  

所有图表都由数据(**data**)，您要可视化的信息以及描述数据变量如何映射到美学属性的映射关系(**mapping**)成。一共包含五个映射组件：  

- 图层(**layer**)是几何元素和统计转换的集合。几何元素（简称**geom **）表示您在图中实际看到的内容，包括点，线，多边形等。统计转换(简称**stat**)，是对数据的汇总：例如，对观测数值分类计数创建直方图，或拟合一个线性模型。  

- **Scale**将数据空间中的值映射到美学空间中，包括颜色、形状和大小等属性的设置。`Scale`还会绘制图例和坐标轴，这使得可以从图中还原原始数据(反向映射)。  

- 坐标系统(**coord**)描述数据坐标如何映射到图形的平面上。它还提供轴线和网格线来帮助查看图片。我们通常使用笛卡尔坐标系，但也有其他一些方法，包括极坐标和地图投影等。  

- 分面(**facet**)指定如何分解数据子集并将其显示为多个小的并列图形。这也被称为条件调节或格子/格架。  

- 主题(**theme**)控制更精细的细节显示，如字体的大小、背景的颜色。尽管ggplot2已经谨慎的选取了默认的参数，但是您可能参考其他资料构建有吸引力的图片。一个很好的起点是塔夫特的早期作品[@tufte:1990; @tufte:1997; @tufte:2001]。  

同样地，需要注意一些事情：  

- 它并没有建议使用哪些图形。虽然这本书致力于推动一个合理的情节制作过程，但重点是如何制作你想要的情节，而不是制作哪一个情节。要想获得更多关于选择或创造情节来回答你感兴趣的问题的建议，你可以咨询@robbins:2004, @cleveland:1993, @chambers:1983, 和 @tukey:1977等人。  

- ggplot2不能绘制交互式图形，只能绘制静态图形。在计算机屏幕上显示ggplot2图与在纸上打印它们本质上没有区别。对于动态和交互式图形，您可以在其他地方寻找(可能是下面描述的`ggvis`)。D@cook:2007为交互式图形包`GGobi`提供了精彩的介绍。`GGobi`可以通过`rggobi`包连接到R[@wickham:2008b]。  

## ggplot2如何适应其他R绘图系统？  

在R中提供了许多其他图形系统：base绘图系统，grid绘图系统和lattice绘图系统。 那么ggplot2与它们有何不同？  

- base绘图系统由Ross Ihaka基于S语言图形驱动程序的经验编写的，部分参考了@chambers:1983。base绘图系统是纸笔模型:您只能在图片的基础上绘制，不能修改或删除现有内容。除了图形在屏幕上的外观之外，没有其他用户可以访问的信息。base绘图系统包括绘制基本图和整个图的工具。base绘图系统的图形绘制通常速度很快，但作用范围有限。如果您已经创建过单个散点图、直方图或一组箱式图，那么您可能已经使用了base绘图系统。  

- grid绘图系统的开发始于2000年，它是一个更加丰富图形原语(graphical primitives)系统。grid绘图系统是由Paul Murrell在他的博士研究中开发出来的[@murrell:1998]。Grid grobs(图形对象)可以独立于plot表示并在以后进行修改。viewports系统(每个视图都包含自己的坐标系统)使布局复杂图形变得更容易。grid绘图系统提供了绘制原语，但没有用于生成统计图形的工具。\index{grid}  

- 由Deepayan Sarkar开发的`lattice`软件包，使用网格图形来实现@cleveland:1993的格子图形系统，与base绘图系统相比有了相当大的改进。您可以很容易地生成图形，一些绘图细节(例如，图例)会被自动处理。然而，lattice绘图系统缺乏标准的模式，这使得它很难扩展。lattice绘图系统在@sarkar:2008中得到了详细的介绍。  

- 始于2005年的ggplot2试图纳入base绘图系统和lattice绘图系统的优点，并使用一个强大的底层模型对它们进行改进，该模型支持基于上面概述的原则生成任何类型的统计图。ggplot2坚实的底层模型使得用紧凑的语法描述广泛的图形变得容易，而独立的组件使扩展变得容易。与lattice一样，ggplot2使用grid来绘制图形，这意味着您可以对情节的外观进行非常底层次的控制。  

- [htmlwidgets](http://www.htmlwidgets.org)提供了一个通用的框架从R访问web可视化工具。建立在htnlwidget之上的包包括：leaflet(<https://rstudio.github.io/leaflet/> 地图)、dygraph(<http://rstudio.github.io/dygraphs/> 时间序列)和networkD3(<http://christophergandrud.github.io/networkD3/> 网络)。  

- [plotly](https://plotly-r.com)是一个流行的带有R接口的javascript可视化工具包。如果您想为HTML文档制作交互式图形，它是一个很棒的工具，甚至还附带了一个`ggplotly()`函数，可以将许多ggplot2图形转换为它们的交互式对等图形。  

许多其他的R包，如vcd[@meyer:2006], plotrix[@plotrix]和gplots[@gplots]实现了专业绘图，但没有其他的提供一个生成统计图形的框架。我们可以在[graphics task](http://cran.r-project.org/web/views/Graphics.html)的列表中找到一个系统包含所有在其他包中存在的绘图工具列表。  

## 关于本书  

第一个章节(第\@ref(getting-started)章)，描述了如何快速开始使用ggplot2制作有用的图形。本章介绍几个重要的ggplot2概念:geoms、aesthetic mappings和facet。  

第\@ref(individual-geoms)章到第\@ref(arranging-plots)章探索如何使用基础的工具箱来解决你在实践中可能遇到的各种各样的可视化问题。  

第\@ref(scale-position)章到第\@ref(scale-other)章向您展示如何控制最重要的比例，允许您调整轴和图例的细节。  

第\@ref(mastery)章描述了作为ggplot2基础的图层语法。第\@ref(layers)章阐述了该理论，演示了如何在你的情节中添加额外的图层，对其中使用的geom和stat进行完全控制。

理解scale是如何运作的对于微调属性至关重要。定制的scale可以很好地控制情节的外观，帮助支持你所讲的故事。第\@ref(scale-position)章，第\@ref(scale-colour)章和第\@ref(scale-other)章将向你展示有哪些scale是可用的，如何调整它们的参数，以及如何控制轴和图例的外观。  

坐标系统和分面控制图形元素的位置将在第\@ref(position)章中描述。分面是一个非常强大的图形工具，它允许您快速比较数据的不同子集。坐标系统不太常用，但对于某些类型的数据来说非常重要。  

为了完善你的故事情节以便出版，你需要学习第\@ref(polishing)章中描述的工具。在那里，您将了解如何控制ggplot2的主题化系统，以及如何将图保存到电脑中。  

## 先决条件 {#prerequisites}  

\index{Installation}  

在我们继续之前，需要确保你有这本书需要的所有软件:  

- **R**：如果你没有安装R，你可能读错了书;我假定在本书中对R有基本的了解。如果你想学习如何使用R，我推荐[《R for Data Science》]((https://r4ds.had.co.nz/))，它旨在让你快速简单的使用R。  

- **RStudio**：RStudio是一个针对R的免费开源集成开发环境(IDE)。虽然你可以在任何R环境(包括R GUI和ESS)下编写和使用R代码，但是RStudio有一些很好的特性专门用于编写和调试你的代码。我们建议您尝试一下，但并不要求ggplot2或本书能够成功。您可以从下面下载RStudio安装程序https://www.rstudio.com/products/rstudio/download 

- **R packages**：这本书使用了一堆R包。你可以通过运行以下命令一次性安装它们:  

  
  
  
  ```r
  install.packages(c(
    "directlabels", "dplyr", "gameofthrones", "ggforce", "gghighlight", 
    "ggnewscale", "ggplot2", "ggraph", "ggrepel", "ggtext", "ggthemes", 
    "hexbin", "mapproj", "maps", "munsell", "ozmaps", "paletteer", 
    "patchwork", "rmapshaper", "scico", "seriation", "sf", "stars", 
    "tidygraph", "tidyr", "wesanderson" 
  ))
  ```

## 其他资源 {#other-resources}  

这本书将教你ggplot2语法的元素以及它们如何组合在一起，但是它并没有完整地记录每个函数的细节。随着ggplot2的使用变得更加复杂和多样化，您将需要额外的文档。  

关于ggplot2函数及其参数的具体细节，最好的参考资料总是内置文档。可以在线访问https://ggplot2.tidyverse.org/reference/index.html ，也可以使用通常的帮助语法在R中访问。在线文档的优点是，您可以看到所有的示例图，并更容易地在主题之间导航。  

如果您经常使用ggplot2，那么注册ggplot2邮件列表http://groups.google.com/group/ggplot2是一个好主意。该列表的流量相对较低，并且对新用户非常友好。另一个有用的资源是[stackoverflow](http://stackoverflow.com)。stackoverflow上有一个活跃的ggplot2社区，许多常见的问题已经被问出来并得到了回答。在这两种情况下，如果您创建一个最小的可重复示例，就更有可能获得帮助。Jenny Bryan的reprex包提供了一种方便的方法来实现这一点，并且还提供了创建一个好例子的建议。您提供的信息越多，社区就越容易帮助您。  

ggplot2中的函数数量可能太多了，但是RStudio提供了一些很棒的备忘单，可以在http://www.rstudio.com/resources/cheatsheets/上提醒您。  

最后，该书的完整源代码可以从https://github.com/hadley/ggplot2-book 在线获得。这包含了这本书的完整文本，以及重建所有情节所需的所有代码和数据。  

## Colophon  

这本书使用[bookdown](http://bookdown.org/)在[RStudio](http://www.rstudio.com/ide/)上进行编辑。[网站](http://ggplot2-book.org/)托管在[netlify](http://netlify.com/)上，并在[Github Actions](https://github.com/features/actions)每次提交后自动更新。 完整的资源可从[GitHub](https://github.com/hadley/ggplot2-book)获得。  

这本书使用R version 4.0.4 (2021-02-15)和以下R包进行构建：  


|package       |version |source         |
|:-------------|:-------|:--------------|
|directlabels  |NA      |NA             |
|dplyr         |1.0.5   |CRAN (R 4.0.4) |
|gameofthrones |NA      |NA             |
|ggforce       |0.3.3   |CRAN (R 4.0.4) |
|gghighlight   |NA      |NA             |
|ggnewscale    |NA      |NA             |
|ggplot2       |3.3.3   |CRAN (R 4.0.3) |
|ggraph        |2.0.5   |CRAN (R 4.0.4) |
|ggrepel       |0.9.1   |CRAN (R 4.0.4) |
|ggtext        |0.1.1   |CRAN (R 4.0.4) |
|ggthemes      |4.2.4   |CRAN (R 4.0.4) |
|hexbin        |1.28.2  |CRAN (R 4.0.4) |
|mapproj       |NA      |NA             |
|maps          |3.3.0   |CRAN (R 4.0.4) |
|munsell       |0.5.0   |CRAN (R 4.0.2) |
|ozmaps        |NA      |NA             |
|paletteer     |NA      |NA             |
|patchwork     |1.1.1   |CRAN (R 4.0.3) |
|rmapshaper    |NA      |NA             |
|scico         |NA      |NA             |
|seriation     |NA      |NA             |
|sf            |NA      |NA             |
|stars         |NA      |NA             |
|tidygraph     |1.2.0   |CRAN (R 4.0.2) |
|tidyr         |1.1.3   |CRAN (R 4.0.4) |
|wesanderson   |NA      |NA             |
