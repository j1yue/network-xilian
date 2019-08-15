# 用计算机系联《广韵》的方法

　　下面说明利用网络分析软件系联《广韵》反切的方法。

## 1. 思路

　　在一张网络图 $G = \{ V, E \}$ 中，包括结点（$V$ ）边（$E$）两个要素，分别讨论如下。

　　**1.1** 目前的研究成果都是以《广韵》中的反切用字为单位进行系联。也就是说，图中的每个结点都代表一个反切用字。显然，这可以规避反切用字不是小韵首字时的失联问题，使操作过程更加简便。但是，传统的系联法却是以小韵为单位系联的。这种办法的好处在于，可以更直观地显示系联时同用、互用、递用基本条例的运用，也更方便我们分析各个小韵的关系，并在此基础上制作韵图。因此，本文提出的方法是以小韵为单位的，每个结点都代表《广韵》中的一个小韵。

　　**1.2** 在分析具体的关联函数之前，我们打算先讨论图是否具有有向性。从目前的研究来看，胡佳佳（[2018](#hujiajia2018)）选择了无向图，而游函（List, [2018](#list2018)）则使用了有向图。有趣的是，两位学者似乎都认为这种选择是不言自明的，并未详细论述[^1]。我们认为，应当以使用有向图为宜。

　　陆志韦（[1963](#luzhiwei1963)）已经指出，在《王三》的反切中，有不少切上字和被切字的声母不符，切下字和被切字的介音不符的反切，并且很多都延续到了《广韵》里。这是由于反切是凭习惯造成的，「全靠作者对于母语有亲切的语音直感」，因此未必完全符合切上字管声母、切下字管韵母和声调这一抽象的音位学分析。换言之，反切上下字的拼读讲求协调、顺口，这一因素在反切用字的选择上起了很大作用。

　　诚然，我们在系联《广韵》时，不得不把切上字和切下字拆分开来，分别考察。但既然反切和被切字之间并不是单纯的等价关系，因此有必要通过有向图的方式加以区分，以便进一步研究的展开。当然，从逻辑上说，在系联时边的具体方向并不重要，只要能够区分被切字和反切用字即可。我们倾向于把被切字当作源结点，把反切当作目标结点。

[^1]: 胡佳佳（[2018](#hujiajia2018): 157）认为，「利用『被切字』与『反切上字』的等价关系划定出的等价类就是《广韵》的声类，利用『被切字』与『反切下字』等价关系划定出的等价类就是《广韵》的韵类。从网络分析的角度，将被切字与反切上字（或下字）看作网络中的结点，被切字与反切上字（或下字）的等价关系看作结点间的无向边（因为等价关系是双向的）」。游函（List, [2018](#list2018): 10）的论证则更嫌草率，只说「反切与被切字的注音系统可以很容易地转化成由反切到被切字的有向图」（The system underlying the *fǎnqiè* spelling, consisting of a *glossed character* and a *glossing character* can be easily translated into a system of *directed networks* in which we draw a link from the glossing character to the glossed character）。

　　**1.3** 

## 2. 材料

　　首先我们先准备《广韵》的电子文档。目前网络上比较易得的有以下三种：

1. [@polyhydron](https://www.zhihu.com/people/polyhedron/) 和 [@有女同车](https://zh.wikipedia.org/zh-hk/User:Blankego) 制作的 `广韵全字表.xlsx`（[2006](http://www.pkucn.com/viewthread.php?tid=175767)）；
2. [@poem](https://www.zhihu.com/people/poem) 制作的 `广韵字音表.xls`（[2017](https://zhuanlan.zhihu.com/p/20430939)）；
3. 游函（Johann-Mattis List）制作的 `guangyun.tsv`（[2018](#list2018)）。

均已调整为 `.csv` 格式并上传至附件，可以根据需要自行选择。

## 3. 步骤



## 参考文献

- <a name="hujiajia2018"></a>胡佳佳 （2018） [网络分析方法在音韵学教学中的应用——以《广韵》反切系联为例](http://kns.cnki.net/KCMS/detail/detail.aspx?dbname=cjfd2018&filename=lyyy201802013&dbcode=cjfq)，《励耘语言学刊》第 2 期，155-165 页。
- <a name="luzhiwei1963"></a>陆志韦 （1963） [古反切是怎样构造的](http://qikan.chaoxing.com/detail_38502727e7500f26ef0c228fd4b949eb9f59f7d6c85e69051921b0a3ea255101fc1cf1fbb4666ae6dd1e65f26d5d83ec532ac29aeda4b1ae11590f99b927935ebee72562d27b55a67245949a1d00025d20b88c6e534e6905ff2392838a1740b511270bb1d955dcf1adfd43ad95f43916)，《中国语文》第 5 期，349-385 页。
- <a name="list2018"></a>List, J.-M. 游函 (2018). [More on network approaches in Historical Chinese Phonology (音韻學)](https://hal.archives-ouvertes.fr/hal-01706927v2/document). Paper prepared for the LFK Society Young Scholars Symposium. Taipei: Li Fang-Kuei Society for Chinese Linguistics. 数据和源代码见. [Source Code Accompanying the Paper "More on network approaches in Historical Chinese Phonology (音韻學)"](http://doi.org/10.5281/zenodo.1171967). Zendo. 