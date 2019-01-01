---
abbrlink: '0'
---
## DNA的二级结构和三级结构

在“**DNA的核苷酸含量**”一文中，我们引入了核酸，并且我们看到核酸的**一级结构**由其核碱基沿着构成核酸聚合物键的**糖-磷酸**主链的有序性决定。然而，一级并没有告诉我们关于分子的更大的三维形状，这对于完全理解核酸是至关重要的。

寻找完整的核酸化学结构是20世纪中叶分子生物学研究的核心，最终于1953年Watson和Crick在*Science*上发表了不到800字的文章。结合由Franklin和Gosling创建的高分辨率X射线图像以及许多已确定的化学结果，Watson和Crick提出了以下DNA结构，也称为**Watson-Crick模型**：


1. DNA分子由两条互相**反向**的链组成； 
2. 每个碱基与相反链中的碱基键合。腺嘌呤总是与胸腺嘧啶结合，胞嘧啶总是与鸟嘌呤结合，**碱基互补**是它始终联系的基础，见图1； 
3. 两股绞合在一起形成一个**双螺旋**的长螺旋形楼梯结构，见图2。

**Figure 1.** Base pairing across the two strands of DNA.

**Figure 2.** The double helix of DNA on the molecular scale.

上述（1）和（2）构成了DNA的**二级结构**，因为它们决定了来自不同链的碱基如何相互作用。（3）描述了DNA分子的三维形状，也就是**三级结构**。

根据Watson和Crick的模型，两个互补碱基的键合称为**碱基对**（bp）。因此，DNA分子的长度通常以bp而不是nt给出。

碱基对是两个核苷酸的组合，其碱基彼此键合并位于DNA分子的相对链上。腺嘌呤与胸腺嘧啶键合，而胞嘧啶与鸟嘌呤键合，如下图所示（说明Watson-Crick碱基配对）。

在转录和翻译期间，RNA参与碱基配对相互作用，在这种情况下尿嘧啶取代胸腺嘧啶，因此形成碱基对AU而不是AT。在RNA折叠期间也可以产生该碱基对。通常我们使用缩写“bp”作为碱基对单元来测量DNA链的长度; 1 bp对应于大约3.4埃。

DNA碱基配对的实际目的是保护重要的DNA分子免受外来键合的影响，这可能会破坏转录。因此，许多研究人员认为DNA实际上是从RNA进化而来的。

DNA的一级结构是由一系列核苷酸A，T，G，C组成的链。根据Watson-Crick模型，DNA的二级结构由与第一条键合的另一条链组成。腺嘌呤仅与胸腺嘧啶键合，胞嘧啶仅与鸟嘌呤键合。因此，A-T，G-C被称为互补碱基对。按照惯例，我们从5'端到3'端读取DNA链。然而，次级链反向存在，因此必须反向读取。因此，我们用其互补碱基替换一条链上的核苷酸，并反向获得二级链。因此通过互补性，一旦我们知道一条链上碱基的顺序，我们就可以立即推断出互补链中的碱基序列。

## 问题

在DNA序列中，符号“A”和“T”是彼此的互补，“C”和“G”也是如此。

DNA序列*s*的反向互补是通过反转*s*的字符然后取每个符号的互补序列*sc*（例如，“GTCA”的互补序列是“TGAC”）。

**Given:** 一条DNA序列*s*

**Return:** *s*的反向互补链*sc*

### 样本数据

```
AAAACCCGGT
```

### 样本输出


```
ACCGGGTTTT
```
## 算法分析

这个问题很简单。只需三个步骤即可完成：

1. 读取DNA链；
2. 反转它（手动或使用编程语言的内置函数）；
3. 遍历反转字符串，将“A”更改为“T”，“C”更改为“G”。

下面给出伪代码：

```pseudocode
input S 
reverse S 
for i = 1 to length of S 
     if S[i] = 'A' then S'[i] = 'T'
     if S[i] = 'T' then S'[i] = 'A'
     if S[i] = 'C' then S'[i] = 'G'
     if S[i] = 'G' then S'[i] = 'C'

print S'
```

在这里我给出具体的两种方法来解决这个问题：

### python

在python中反转一条字符串可以通过索引来解决，也就是`string[::-1]`，接着使用`for`循环遍历反转后的字符串并使用在之前一篇文章中提到的`string.replace()`函数即可；关于替换字符还有另外一个方法，可以利用字典对象定义一个替换规则：

```python
rules = {"A":"T", "T":"A", "C":"G", "G":"C"}
```

下面给出示例代码：

```python
def complement_strand(string):
    rules = {"A":"T", "T":"A", "C":"G", "G":"C"}
    return "".join(rules[i] for i in string[::-1])
```

In [1]:

```python
print(complement_strand("AAAACCCGGT"))
```

Out[1]:

```python
ACCGGGTTTT
```

### bash

在bash下，我们可以通过命令`rev`来反转字符串，然后通过之前一篇文章提过的命令`tr`来替换字符，相当的简介！下面给出命令`rev`的语法，只需要在命令后面接上需要操作的字符即可。

```bash
NAME
       rev - reverse lines characterwise

SYNOPSIS
       rev [option] [file...]
```

In [1]:

```bash
## sample_rna_seq.txt is AAAACCCGGT
rev sample_rna_seq.txt | tr ATCG TAGC
```

Out[1]:

```bash
ACCGGGTTTT
```

