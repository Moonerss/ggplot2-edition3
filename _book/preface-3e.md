# 第三版前言 {#preface-3e .unnumbered}  

欢迎阅读第三版的《ggplot2:数据分析与图形艺术》。我很高兴能针对ggplot2在过去五年中发生的所有变化更新该书的新版本。我也很高兴终于有了这本书的在线版本，<http://ggplot2-book.org/>，这要归功于与Springer出版社的重新洽谈。  

自该书的上一版以来，ggplot2本身的主要变化是来自社区贡献者。尽管我目前仍领导该项目并继续关注数据可视化，但我不再参与该程序包的日常开发。在撰写本文时，ggplot2的核心开发人员是：  

-   [Winston Chang](https://github.com/wch)
-   [Lionel Henry](https://github.com/lionel-)
-   [Thomas Lin Pedersen](https://github.com/thomasp85)
-   [Kohske Takahashi](https://github.com/kohske)
-   [Claus Wilke](https://github.com/clauswilke)
-   [Kara Woo](https://github.com/karawoo)
-   [Hiroaki Yutani](https://github.com/yutannihilation)
-   [Dewey Dunnington](https://github.com/paleolimbot)

您可以在[ggplot2官方文档](https://github.com/tidyverse/ggplot2/blob/master/GOVERNANCE.md)中查看最新的成员列表以及如何成为核心开发成员。  

## 主要变化 {.unnumbered}  

- 删除了*Data Analysis, Data Transformation, and Modelling for Visualisation*章节，使本书更加专注于可视化。如果您正在寻找有关在R中进行数据科学的一般建议，那么我建议您阅读[R for Data Science](https://r4ds.had.co.nz)。   

- *Toolbox*被添加到第六章，用来练习对图层的使用。其中包括有关地图和注解的更多相关材料，以及一个新的章节讨论如何在一页上排列多个图。  

- 相似的，旧的*Scales, Axes, and Legend*章节被分成四个章节，前三个章节包含了对量表数据的标化和使用指南，最后一个章节关注于理论基础。  

- 旧的*Positioning*一章已分为新的*Coordinate Systems*和*Faceting*两章，为这些重要话题提供更多的空间。  

- 新的章节详细介绍了ggplot2的内部结构，以及如何在自己的程序包中对其进行扩展。  

## 致谢 {.unnumbered}  

在书的该版本当中，有两位新合著者：Danielle Navarro和Thomas Lin Pedersen。 Danielle在图层和标化章节中贡献了大多数新的内容，而Thomas在关于拼图（使用他的`patchwork`包）以及如何扩展ggplot2方面贡献了新的章节。  

本书是公开编写的，并在完成后会在Twitter上刊登各章的广告。这确实是社区的力量：许多人阅读草稿，检阅错字，建议改进，提供内容。没有这些贡献者，这本书的质量将不尽如人意。我非常感谢他们的帮助。




```
## Warning in scan(file = file, what = what, sep = sep, quote = quote, dec = dec, :
## invalid input found on input connection 'contributors.csv'
```

非常感谢通过GitHub拉取请求做出特定改进的所有12 个人（按用户名的字母顺序）: Alexej Gossmann (\@agisga), \@chriselrod, Carson Sievert (\@cpsievert), Dave Childers (\@davechilders), \@dicorynia, Dennis Murphy (\@djmurphy420), Danielle Navarro (\@djnavarro), \@dmurdoch, Zhuoer Dong (\@dongzhuoer), Dan Yavorsky (\@dyavorsky), Francisco Júnior (\@fjuniorr), G (\@gokceneraslan).
