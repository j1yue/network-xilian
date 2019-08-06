# 网络分析方法及其在古汉语研究中的应用述要

**摘要**：

**关键词**：网络分析；系联；上古音

## 1. 网络分析的基本概念

　　1.1 简而言之，**网络**（network）是由线段连接在一起的点的集合，在物理学、生物学和社会学等领域中都有广泛的应用。按照图论（graph theory）的术语，各个点被称作**顶点**（vertices）或**结点**（nodes），而连接结点的线段称之为**边**（edges），如图所示（引自 Newman, [2010](https://www.oxfordscholarship.com/view/10.1093/acprof:oso/9780199206650.001.0001/acprof-9780199206650)）：

![](pic/vertices-and-nodes.png)

　　1.2 一个**网络图**（graph）可以用 $G=(V, E)$ 的形式表示。其中，结点的集合记作：

$$V(G) = \{ v_1, v_2, v_3, ..., v_n \}$$

边的集合记作：

$$E(G)=\{e_1, e_2, e_3, ..., e_n\}$$

　　1.3 结点可以直接用小写字母表示。对于两个结点 $u,v \in V$ 所组成的边，在无向（undirected）图中记作 $\{u,v\}$，在有向（directed）图中则记作 $(u,v)$；在不必区分时，可以直接简写成 $u v$（参见 Brandes & Erlebach, [2005](https://link.springer.com/book/10.1007/b106453): §2.1）。

## 2. 网络图的实现方法

　　2.1 通过计算机制作网络图的方法很多，主要有以下几类：

1. [Python](https://www.python.org/) 语言，需要配合 [NetworkX](http://networkx.github.io/) 和 [Matplotlib](https://matplotlib.org/) 等扩展包（package）；
2. [JavaScript](https://www.javascript.com) 脚本，较为流行的有 [ECharts.js](http://echarts.baidu.com/)、[Jexf.js](https://github.com/raphv/gexf-js)、[Sigma.js](http://sigmajs.org/) 或 [Vis.js](https://visjs.org/) 等；
3. 其他网络分析及其可视化软件，如 [AllegroGraph](https://allegrograph.com/)、[Gephi](https://gephi.org/) 、[NetMiner](http://www.netminer.com/main/main-read.do) 等。

除此之外，还有 [R](https://www.r-project.org/) 语言等也可以实现类似的效果，具体情况可以参见维基百科的 [en:Social network analysis software](https://en.wikipedia.org/wiki/Social_network_analysis_software) 词条。

　　由于篇幅所限，这里不打算介绍其具体的操作方法（可以参见[附录](#5.-附录)），只是对上述这三种方式的优缺点进行简要的评述。

　　2.2 作为一门编程语言，Python 的使用需要安装相应的环境，而且所有设置都需要以编程命令的形式完成，因此相对而言直观性较差，学习和使用成本较高。但也正得益于此，Python 具有更强的可定制性，加之其开源、活跃的社区，让使用者可以根据自己的实际需要灵活调整其配置，并直接编写相关程序以展开后续的数据分析工作。

　　通过 JavaScript 实现网络图制作与分析的脚本很多，选择丰富，其使用方式也不尽相同。总体说来，使用 JavaScript 同样要安装一定编程环境，还需要一些 HTML/CSS 的基础知识。但 JavaScript 作为一门 Web 编程语言，被广泛运用于几乎所有现代的 HTML 网页上，因而虽然处理数据的能力稍弱，但十分便于生成结果的查看和共享。

　　在网络分析软件中，Gephi 有较为直观的图形化界面，



## 3. 网络分析方法与音韵学

### 3.1 音韵学

　　3.1.1 游函（List, [2016a](https://doi.org/10.1163/2405478X-00902004)）最早用网络分析方法系联了《诗经》押韵。

　　3.1.2 游函（List, [2018](https://hal.archives-ouvertes.fr/hal-01706927v2/document)）利用网络分析方法对《广韵》中反切上字的分组现象作了考察。胡佳佳（[2018](http://kns.cnki.net/KCMS/detail/detail.aspx?dbname=cjfd2018&filename=lyyy201802013&dbcode=cjfq)）从音韵学教学的角度，介绍了网络分析方法在系联反切上字和下字时的作用。

### 3.2 文字学

　　我们知道，形声字中包含着丰富的古音信息，为上古音研究提供了重要线索；但同时其信息又是十分复杂的，需要仔细甄别，特别是在声母方面，更是「言人人殊」，必须要持谨慎态度（耿振生, 2004: §3）。网络分析方法的直观性，可以为我们更准确地认识谐声系统提供很多帮助。西方学者游函和丘内藤在这方面做出了初步的尝试[^3.2]。

[^3.2]: 尽管这两位学者的研究仍是以上古音为主要目标，但我们将其单独列为「文字学」一节。因为研究时所用的材料和侧重与前一节本就有所不同，同时，也是希望更多地展示网络分析方法应用的空间和领域。

　　3.2.1 蒲立本把上古汉语的音节分成两类，A 类是中古的非三等，B 类是中古的三等，有前腭介音 -*j*-。沙加尔（Sagart, [1999](https://doi.org/10.1075/cilt.184): §§2.7, 3.3.2）认为这两种类型和谐声系列有关。比如，在下图（引自 List, [2018](https://hal.archives-ouvertes.fr/hal-01706927v2/document): 7）中，蓝色的结点属于 A 类，黄色的结点属于 B 类：

![](/pic/xiesheng.png)

　　游函（List, [2018](https://hal.archives-ouvertes.fr/hal-01706927v2/document): §2.1）利用 Python 语言，分析了高本汉（Karlgren, [1957](http://ss.zhizhen.com/detail_38502727e7500f26f1ce104a15568ce8e2ee8db6d8d18d4d1921b0a3ea255101ff20232bc5d7271392ca6eb2c71318865155c5438fbb21eab02f26b59238cf601ee603dc6f3d002408283ada86f7e698?)）归纳的 625 组谐声系列。如果某一组类中超过 70% 的字属于中古的三等，那么就归入上古的 B 类；反之，如果不到 30% 的字属于中古三等，则将其归入上古的 A 类。在这样的条件下，游函找到了 16 组谐声偏旁符合这一规律，其中 8 组是「十分显著」的例子（完整的列表参见原文附录 B）。

　　3.2.2 游函、丘内藤（List & Hill, [待刊](http://lingulist.de/documents/papers/hill-list-2019-chinese-character-formation-graphs.pdf)）

### 3.3 训诂学

　　目前，网络分析方法在训诂学中的应用还比较有限。据我们了解，只在北京师范大学汉字研究与现代应用实验室制作的汉字全息资源应用系统（[2019](http://qxk.bnu.edu.cn/)，以下简称「全息库」）中有所应用。

　　全息库在「专书检索」选项卡「综合系联」中的「训释系联」里，使用了 JavaScript 的 [vis.js](https://github.com/visjs/vis-network) 插件，以实现《说文》《尔雅》《释名》《方言》四本最为重要的小学专书中训释词和被训释词的自动系联，如图所示：

![](/pic/qxk.png)

不难看出，在左侧的菜单里可以自行设定被释词或训释词，并选择系联的范围和层级（最小为 1，最大为 5）。无疑，这一系统对我们更好地认识、分析词义系统是很有帮助的。但遗憾的是，全息库中的「构型系联」和「古音系联」都只是线性的列表，没有采用网络分析这一形式。

## 4. 结语



## 5. 附录

　　制作网络图的三种工具，其操作方法分别参见 [Python](python.md)、[Javascript](js.md) 和 [Gephi](gephi.md)。



## 参考文献

- 北京师范大学汉字研究与现代应用实验室 （2019）汉字全息资源应用系统，http://qxk.bnu.edu.cn/。访问日期：2019 年 8 月 4 日。
- 耿振生 （2004） 《20 世纪汉语音韵学方法论》，北京大学出版社。
- 胡佳佳 （2018） [网络分析方法在音韵学教学中的应用——以《广韵》反切系联为例](http://kns.cnki.net/KCMS/detail/detail.aspx?dbname=cjfd2018&filename=lyyy201802013&dbcode=cjfq)，《励耘语言学刊》第 2 期，155-165 页。
- Brandes, Ulrik & Erlebach Thomas eds. (2005): [*Network Analysis: Methodological Foundations*](https://link.springer.com/book/10.1007/b106453). Berlin, Heidelberg: Springer-Verlag.
- Hill, Nathan W. & List, Johann-Mattis (forthcoming): [Using Chinese character formation graphs to test proposals in Chinese historical phonology](http://lingulist.de/documents/papers/hill-list-2019-chinese-character-formation-graphs.pdf). *Bulletin of Chinese Linguistics*, 1-16.
- Karlgren, Bernhard (1957): [Gramma Serica Recensa](http://ss.zhizhen.com/detail_38502727e7500f26f1ce104a15568ce8e2ee8db6d8d18d4d1921b0a3ea255101ff20232bc5d7271392ca6eb2c71318865155c5438fbb21eab02f26b59238cf601ee603dc6f3d002408283ada86f7e698?). *Bulletin of the Museum of Far Eastern Antiquities*, 29. 汉译本见高本汉：《[汉文典](http://ss.zhizhen.com/detail_38502727e7500f26ea2dfaed11771665fed4b47e2deecb0f1921b0a3ea25510134114c969f2eae5cc744720e3130b751ed88dfe5746c33d69cb51d43696fa7ef69b6d1a0a8fc4207fba42c3daf60db7d?&apistrclassfy=0_8_2)》，潘悟云、杨剑桥、陈重业、张洪明译，上海辞书出版社，1997。
- List, Johann-Mattis (2016a): [Using Network Models to Analyze Old Chinese Rhyme Data](https://doi.org/10.1163/2405478X-00902004). *Bulletin of Chinese Linguistics*, 9(2), 218-241.
- —— (2016b). digling/shijing: Data and Code for the Shījīng Network Analysis (Version v1.0). Zenodo. http://doi.org/10.5281/zenodo.167341
- —— (2018): [More on network approaches in Historical Chinese Phonology](https://hal.archives-ouvertes.fr/hal-01706927v2/document). Paper prepared for the LFK Society Young Scholars Symposium. Taipei: Li Fang-Kuei Society for Chinese Linguistics.
- Newman, Mark E.J. (2010): [*Networks: an Introduction*](https://www.oxfordscholarship.com/view/10.1093/acprof:oso/9780199206650.001.0001/acprof-9780199206650). New York: Oxford University Press.
- Sagart, Laurent (1999): [*The Roots of Old Chinese*](https://doi.org/10.1075/cilt.184). Philadelphia: John Benjamins. 汉译本见沙加尔：《[上古汉语词根](http://ss.zhizhen.com/detail_38502727e7500f264b1a17c7914b5b8eb7d8e42d1448219a1921b0a3ea25510134114c969f2eae5cd8a964fdd6ecd3537ea0d09aa8e546031ebd9f0dd9d277dcf3cd01ab5af9a03019ea194ccb5b9f2e?&apistrclassfy=0_8_2)》，龚群虎译，上海教育出版社，2004。