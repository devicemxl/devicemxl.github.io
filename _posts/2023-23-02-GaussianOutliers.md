---
layout: category-post
title:  "Jaccard"
date:   2023-02-22
categories: writing
---

# The Jaccard similarity coefficient

Hello, I intend to make an amazingly simple explanation about the Jaccard index: it is a measure of similarity, it measures the similarity between two sets of information. The Jaccard similarity coefficient was created by Grove Karl Gilbert in 1884 and has the most diverse applications from [behavioral research](https://basurafernando.github.io/papers/AnticipationCVPR21.pdf) to [stability of unicellular clusters](https://pubmed.ncbi.nlm.nih.gov/33165513/), obviously going through the NPL. To understand clearly you need to study a bit of set theory, or if you're a SQL coder it can be interpreted as the measure of an inner join.

![Venn](https://github.com/devicemxl/devicemxl.github.io/blob/master/_posts/imgs/20232202jaccard.002.png?raw=true)

I know sometimes is very innecesary learn all that things, sure?

To get started in python we need to define two sets, obviously after loading the libraries.

```python
# libraries
import matplotlib.pyplot as plt
import matplotlib_venn as venn
```

```python
GroupA = {1, 2, 3}
GroupB = {3, 4, 5}
```

To see the ven diagrams we use the matplotlib_venn library

```python
venn.venn2([GroupA, GroupB], set_labels=('Group A','GroupB'))
plt.show()
```

![Venn Intersection](https://github.com/devicemxl/devicemxl.github.io/blob/master/_posts/imgs/20232202jaccard.003.png?raw=true)

```python
# Intersection method
#
Intersection = GroupA.intersection(GroupB)
print("Intersection of GroupA and GroupB:", Intersection)
```

Intersection of GroupA and GroupB: {3}


Now we can see how the intersection of the two datasets are in "3", then to calculate the jaccard we need follow the formula:

![JaccardFormula](https://github.com/devicemxl/devicemxl.github.io/blob/master/_posts/imgs/20232202jaccard.001.svg?raw=true)

And the expression can be canceptually translated as:

```math

Jaccard = Intersection / ( GroupA + GroupB - Intersection )

Jaccard = 1 / ( 3 + 3 - 1)
Jaccard = 1/5
Jaccard = 0.2

```

In python a specific code can be:

```python
# specific code
#
len(Intersection) / ( len(GroupA) + len(GroupB) - len(Intersection) )
```

Of course generally you need to compare list of items, then you need make loop in the Source list to compare in each record of the comparison list. I make a little code for this. you can review, enjoy and make corrections. Always are welcome!


The notebook version of this text: [Notebook](https://github.com/devicemxl/devicemxl.github.io/blob/master/_posts/jupyter/20232202-jaccard.ipynb)


The code of jaccard: [exercise](https://github.com/devicemxl/ETL-Helper/blob/raiz/TextTools.py)


```html

```