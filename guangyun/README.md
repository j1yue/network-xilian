# 用计算机系联《广韵》韵类

　　本文打算说明利用网络分析软件系联《广韵》反切下字的方法。

## 1. 思路

　　在一张网络图 $G = \{ V, E \}$ 中，包括结点 $V$ 和边 $E$ 两个要素，分别讨论如下。

　　**1.1** 目前的研究成果都是以《广韵》中的反切用字为单位进行系联。也就是说，图中的每个结点都代表一个反切用字。显然，这可以规避反切用字不是小韵首字时的失联问题，使操作过程更加简便。但是，传统的系联法却是以小韵为单位系联的。这种办法的好处在于，可以更直观地显示系联时同用、互用、递用基本条例的运用，也更方便我们分析各个小韵的关系，并在此基础上制作韵图。因此，本文提出的方法是以小韵为单位的，每个结点都代表《广韵》中的一个小韵。

　　**1.2** 在分析具体的关联函数之前，我们打算先讨论图是否具有有向性。从目前的研究来看，胡佳佳（[2018](#hujiajia2018)）选择了无向图，而游函（List, [2018](#list2018)）则使用了有向图。有趣的是，两位学者似乎都认为这种选择是不言自明的，并未详细论述[^1]。我们认为，应当以使用有向图为宜。

　　陆志韦（[1963](#luzhiwei1963)）已经指出，在《王三》的反切中，有不少切上字和被切字的声母不符，切下字和被切字的介音不符的反切，并且很多都延续到了《广韵》里。这是由于反切是凭习惯造成的，「全靠作者对于母语有亲切的语音直感」，因此未必完全符合切上字管声母、切下字管韵母和声调这一抽象的音位学分析。换言之，反切上下字的拼读讲求协调、顺口，这一因素在反切用字的选择上起了很大作用。

　　诚然，我们在系联《广韵》时，不得不把切上字和切下字拆分开来，分别考察。但既然反切和被切字之间并不是单纯的等价关系，因此有必要通过有向图的方式加以区分，以便进一步研究的展开。当然，从逻辑上说，在系联时边的具体方向并不重要，只要能够区分被切字和反切用字即可。

[^1]: 胡佳佳（[2018](#hujiajia2018): 157）认为，「利用『被切字』与『反切上字』的等价关系划定出的等价类就是《广韵》的声类，利用『被切字』与『反切下字』等价关系划定出的等价类就是《广韵》的韵类。从网络分析的角度，将被切字与反切上字（或下字）看作网络中的结点，被切字与反切上字（或下字）的等价关系看作结点间的无向边（因为等价关系是双向的）」。游函（List, [2018](#list2018): 10）的论证则更嫌草率，只说「反切与被切字的注音系统，可以很容易地转化成由反切到被切字的有向图」（The system underlying the *fǎnqiè* spelling, consisting of a *glossed character* and a *glossing character* can be easily translated into a system of *directed networks* in which we draw a link from the glossing character to the glossed character）。

　　**1.3** 下面我们以反切下字的系联为例，讨论关联函数 $\psi$ 的设置。前面已经说到，如果以切下字为结点系联，是很容易实现的，即：

$$\psi_G = (V_R, V_R' ) \tag{1}$$

其中，$V_R$ 是《广韵》中出现的全部反切下字，$V_R'$ 是 $V_R $ 所用的反切下字。显然 $V_R' \subseteqq V_R$，因此全部结点都可以直接相联。

　　而我们如果要以小韵为结点系联，理想状态下应该有：

$$\psi_G=(U, V_R) \tag{2.1}$$

其中，$U$ 表示《广韵》中的所有小韵首字，而 $V_R$ 则是其相应的反切下字。但实际上，《广韵》中的反切下字并不一定都是小韵的代表字；也就是说，既然 $V_R \not\sub U$，也就必然存在一个小韵的集合 $U_0$，其对应的切下字 $V_0 = \{ v\ |\  v \in V_R 且 v \notin U \}$，不能和 $V_0$ 所在小韵 $U_R$ 系联为一类。

　　比如，一东韵中的「穷，去宫切」，「宫」所在小韵的代表字是「弓」，因此「穷」本应和「弓」小韵系联为一类。但因为「穷」所用的反切下字「宫」并非小韵首字，如果直接按照式 $(2.1)$ 的关联函数运行程序，就会导致这一类小韵的失联。因此在出现这种情况时，我们需要让计算机查找出 $V_0$ 这些反切下字所在小韵的代表字 $U_R$，即：

$$\psi_G = \begin{cases} (U, V_R), &V_R \sub U \\ (U, U_R), &V_R \not\sub U \end{cases} \tag{2.2}$$

　　在具体实践中，我们可以让计算机自动检索 $V_0$ 中所有结点所对应的 $U_R$，并将 $U_R$ 替换为目标结点。此外，还有一种更简单的办法：既然《广韵》中的每个小韵都和一个音节一一对应，那么我们可以把所有结点都以音标或序号的形式储存；这样一来，$V_0$ 和 $U_R$ 对计算机而言就是相同的两个结点，自然也就绕过了上述问题，可以直接系联起来了。这种方法还有另一个好处：只要原始数据处理得当，就可以很好地规避多音字的识别，这也是此前研究都悬而未决的问题。

　　**1.4** 以上是对陈澧《切韵考》中基本条例的应用。除此之外，陈澧还发明了分析条例和补充条例。其中，分析条例是把可能系联而实际上不同类的反切上下字区分开来；而补充条例则是用来解决实际上不同类却不能直接系联的情况，有「又音互见定声类」和「四声相承定韵类」两种（耿振生, [2004](#gengzhensheng2004): 35-40）。这两种方法在之前的研究中也没能得到很好的解决。

　　众所周知，「四声相承」作为一种类比推理，在逻辑上并不严谨，难于贯彻，因而暂且不论。「又音互见」的办法，==【我还没想呢】==。至于分析条例，我们由于技术所限，目前也还不能将其完全自动化，只能尽量清晰地将其显示出来后再手动处理、调整。

## 2. 材料准备

　　我们要先准备《广韵》的电子文档，作为素材。目前网络上比较易得的有以下三种：

1. [@polyhydron](https://www.zhihu.com/people/polyhedron/) 和 [@有女同车](https://zh.wikipedia.org/zh-hk/User:Blankego) 制作的 `广韵全字表.xlsx`（[2006](http://www.pkucn.com/viewthread.php?tid=175767)）；
2. [@poem](https://www.zhihu.com/people/poem) 制作的 `广韵字音表.xls`（[2017](https://zhuanlan.zhihu.com/p/20430939)）；
3. 游函（Johann-Mattis List）制作的 `guangyun.tsv`（[2018](#list2018)）。

我们这里选择的是数据最为完善的《广韵字音表》，并保存为 `poem-2017.csv`；再利用 Excel 的高级筛选功能，筛选出所有小韵，如图所示：

![](pic/shaixuan-xiaoyun.png)

将结果复制到新的表格中，保存为 `xiaoyun.csv`。注意：在使用 Excel 的另存为功能生成 `.csv` 文件时，保存类型应该选择 `CSV UTF-8 (逗号分隔) (*.csv)` 而非  `CSV (逗号分隔) (*.csv)`，这样可以防止汉字字符的编码错误。

　　**2.2** 我们先编辑结点的数据。用 Excel 新建一个 `nodes.csv` 文件，在第一行中输入表头：

````csv
Id,Label,Initial,Rhyme,Deng_hu,Char_num
````

在第二行里分别输入（为了醒目其间，这里分为六行）：

````csv
=xiaoyun.csv!AV2,
="【"&xiaoyun.csv!X2&"】"&xiaoyun.csv!V2&xiaoyun.csv!W2,
=xiaoyun.csv!AE2,
=xiaoyun.csv!AM2&xiaoyun.csv!AN2,
=xiaoyun.csv!AF2&xiaoyun.csv!AG2&RIGHT(xiaoyun.csv!AU2, 1),
=xiaoyun.csv!AB3-xiaoyun.csv!AB2
````

然后利用 Excel 的快速填充功能，拖拽至工作表的第 3819 行，结果如下所示：

````csv
Id,Label,Initial,Rhyme,Deng_hu,Char_num
tung,【東】德紅,端,上平01東,開一,17
dung,【同】徒紅,定,上平01東,開一,45
triung,【中】陟弓,知,上平01東,開三,4
driung,【蟲】直弓,澄,上平01東,開三,7
cjung,【終】職戎,章,上平01東,開三,15
...
phyap,【𥎰】孚法,滂,上平01乏,合三,3
nriap,【䎎】女法,娘,上平01乏,開三,3
thriap,【𦑣】丑法,徹,上平01乏,開三,1
````

　　各列的说明如下：

1. `Id`：我们使用的是网络上流传较广的 [@polyhedron](http://zh.wikipedia.org/zh/User:Polyhedron) 版中古汉语拼音（[2005/2019](#polyhedron2005)）而非汉字，理由见上 [§1.3](1-思路) 节；
2. `Label`：包括小韵首字和反切；
3. `Initial`：声母；
4. `Rhyme`：韵目；
5. `Deng_hu`：等、开合；
6. `Char_num`：小韵收字。因为原表中没有《广韵》中各小韵的字数，所以我们用相邻两个字的《广韵》字序作了运算得到收字数。最后一个「𦑣」小韵的字数要在原表下的 `AB3819` 单元格补充数字 `25318`，才能得出正确的值。

　　**2.4** 下面我们编辑边的数据。类似地，新建文件 `edges.csv`，输入表头：

````csv
Id,Source,Target,Type,Weight
````

在各列中分别输入：

````csv
1,
=xiaoyun.csv!AV2,
=xiaoyun.csv!DC2,
Directed
=COUNTIF($C$2:$C$3819, B2)+1
````

并填充至最后一行，结果如下所示：

````csv
Id,Source,Target,Type
1,tung,ghung,Directed,12
2,dung,ghung,Directed,12
3,triung,kiung,Directed,7
4,driung,kiung,Directed,7
5,cjung,njung,Directed,5
...
3816,phyap,pyap,Directed,0
3817,nriap,pyap,Directed,0
3818,thriap,pyap,Directed,0
````

其中 `Source` 是《广韵》中的全部小韵首字 $U$ 的中古汉语拼音（也就是 `nodes.csv` 中的 `Id` 一列）；`Target` 是其反切下字 $V_R$ 的拼音。 最后一列 `Type` 计算了这个反切下字

## 3. 生成结果

　　把上述数据保存后分别导入 Gephi 软件，经过对外观和布局适当的调整后，《广韵》全书反切下字系联的结果就如图所示：

![](pic/rhyme-whole.png)





## 参考文献

- <a name="gengzhensheng2004"></a>耿振生 （2004） 《20 世纪汉语音韵学方法论》，北京大学出版社。
- <a name="hujiajia2018"></a>胡佳佳 （2018） [网络分析方法在音韵学教学中的应用——以《广韵》反切系联为例](http://kns.cnki.net/KCMS/detail/detail.aspx?dbname=cjfd2018&filename=lyyy201802013&dbcode=cjfq)，《励耘语言学刊》第 2 期，155-165 页。
- <a name="luzhiwei1963"></a>陆志韦 （1963） [古反切是怎样构造的](http://qikan.chaoxing.com/detail_38502727e7500f26ef0c228fd4b949eb9f59f7d6c85e69051921b0a3ea255101fc1cf1fbb4666ae6dd1e65f26d5d83ec532ac29aeda4b1ae11590f99b927935ebee72562d27b55a67245949a1d00025d20b88c6e534e6905ff2392838a1740b511270bb1d955dcf1adfd43ad95f43916)，《中国语文》第 5 期，349-385 页。
- <a name="polyhedron2005"></a>"Polyhedron" （2005/2019） [User:Polyhedron/中古汉语拼音](https://zh.wikipedia.org/wiki/User:Polyhedron/%E4%B8%AD%E5%8F%A4%E6%BC%A2%E8%AA%9E%E6%8B%BC%E9%9F%B3)，维基百科。访问日期：2019 年 8 月 16 日。
- <a name="list2018"></a>List, J.-M. 游函 (2018). [More on network approaches in Historical Chinese Phonology (音韻學)](https://hal.archives-ouvertes.fr/hal-01706927v2/document). Paper prepared for the LFK Society Young Scholars Symposium. Taipei: Li Fang-Kuei Society for Chinese Linguistics. 数据和源代码见. [Source Code Accompanying the Paper "More on network approaches in Historical Chinese Phonology (音韻學)"](http://doi.org/10.5281/zenodo.1171967). Zendo. 
- 