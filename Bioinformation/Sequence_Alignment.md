[TOC]

# 计算DNA的核苷酸

## 分子生物学简介

构成所有生物原料的**细胞**被认为是生命的基石。**细胞核**是大多数**真核细胞**的组成部分，150年前被确定为细胞活动的中心。在光学显微镜下观察，细胞核仅作为细胞的较暗区域出现，但随着我们增加放大倍数，我们发现细胞核密集地充满了称为**染色质**的大分子物质。在**有丝分裂**期间（真核细胞分裂），大多数染色质浓缩成长而细的细胞串，称为**染色体**。有关有丝分裂不同阶段的细胞图见下图。

![Figure 1. A 1900 drawing by Edmund Wilson of onion cells at different stages of mitosis. The sample has been dyed, causing chromatin in the cells (which soaks up the dye) to appear in greater contrast to the rest of the cell.](https://github.com/zomath/python/raw/3bdee0b8e6e28a27e45dd3ec2c5fdf3ddd67cc2a/Bioinfo/Images/001.png)

**图1.** 在1900年Emmund Wilson在有丝分裂不同阶段绘制的洋葱细胞图。由于样品已被染色，导致细胞中的染色质（吸收染料）与细胞的其他部分形成鲜明对比。

染色质中含有的一类大分子称为**核酸**。20世纪早期对核酸化学特性的研究最终得出结论：核酸是**聚合物**，或者将这种重复结构的称为**单体**。由于它们细而长，核酸聚合物通常被称为**链**。

核酸单体称为**核苷酸**，并作为链长度的单位（缩写为*nt*）。每个核苷酸由三部分组成：**糖分子**，带有负离子的**磷酸盐**，和**核碱基**化合物（简称“碱基”）。当一个核苷酸的糖与链中下一个核苷酸的磷酸键合时开始聚合，其形成核酸链的**糖-磷酸骨架**。关键点在于特定类型核酸的核苷酸总是含有相同的糖和磷酸盐分子，它们的区别仅在于它们对碱基的选择。因此，核酸的一条链可以仅基于其碱基的顺序与另一条链区分开;碱基的这种排序定义了核酸的**一级结构**。

例如，图2显示了**脱氧核糖核酸**（DNA）链，其中糖被称为**脱氧核糖**，分别有四种碱基：**腺嘌呤**（A），**胞嘧啶**（C），**鸟嘌呤**（G）和**胸腺嘧啶**（T）。

![Figure 2. A sketch of DNA's primary structure.](https://github.com/zomath/python/raw/3bdee0b8e6e28a27e45dd3ec2c5fdf3ddd67cc2a/Bioinfo/Images/002.png)

**图2.** DNA的一级结构示意图。

DNA存在于地球上的所有生物体中，包括细菌;它甚至存在于许多通常被认为是非生命的病毒中。由于其重要性，我们使用“**基因组**”来指代生物体染色体中包含的DNA的总和。

## 问题

在探索分子生物学的道路上，DNA中所蕴含的信息是至关重要的，由前文我们可以知道一条DNA链仅有A，T，C，G四种碱基决定的核苷酸序列构成，因此了解一条DNA链中四种核苷酸的含量是非常关键的一步！

**Given:** A DNA string s of length at most 1000 nt.

**Return:** Four integers (separated by spaces) counting the respective number of times that the symbols 'A', 'C', 'G', and 'T' occur in *s*.

## 样本数据集

```
AGCTTTTCATTCTGACTGCAACGGGCAATATGTCTCTGTGTGGATTAAAAAAAGAGTGTCTGATAGCAGC
```

## 样本输出

```
20 12 17 21
```

In [1]:

```python
## 加载样本数据
with open("Bioinformatics_Stronghold/data/rosalind_dna.txt", "r") as r_dna:
    r_dna = r_dna.read()
```

In [2]:

```python
## 在这里我们可以使用python的字符串自带的一个属性（.count()）来实现此算法
print(r_dna.count("A"))
```

Out[2]:

```python
243
```

In [3]:

```python
def count_DNA(string):
    return string.count("A"), string.count("C"), string.count("G"), string.count("T")
```


In [4]:

```python
print(count_DNA(r_dna))
```

Out[4]:

```python
(243, 228, 221, 231)
```

最后如果对生物信息学算法感兴趣的小伙伴可以关注我在github上的项目：

```
https://github.com/zomath/python/tree/master/Bioinfo
```