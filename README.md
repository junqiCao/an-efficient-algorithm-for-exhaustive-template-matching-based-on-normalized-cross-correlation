# an-efficient-algorithm-for-exhaustive-template-matching-based-on-normalized-cross-correlation
record the content of  this article

本文中的NCC公式如下，该公式与halcon中使用的公式有差别

$$
NCC(x, y)=\frac{\sum_{j=1}^{N} \sum_{i=1}^{N} I(x+i, y+j) \cdot T(i, j)}{\sqrt{\sum_{j=1}^{N} \sum_{i=1}^{M} I(x+i, y+j)^{2}} \cdot \sqrt{\sum_{j=1}^{N} \sum_{i=1}^{M} T(i, j)^{2}}}
$$
这里利用$\beta(x, y)$来作为$C(x,y)$的最大值，其中$C(x,y)$为

$$
C(x, y)=\sum_{i=1}^{N} \sum_{i=1}^{M} I(x+i, y+j) \cdot T(i, j)
$$
可以得出以下公式：
$$
\beta(x, y) \geq C(x, y)=\sum_{j=1}^{N} \sum_{i=1}^{M} I(x+i, y+j) \cdot T(i, j)
$$
对该公式进行变形可以得到以下公式:
$$
\frac{\beta(x, y)}{|I(x, y)|_{2} \cdot|T|_{2}} \geq \frac{C(x, y)}{|I(x, y)|_{2} \cdot|T|_{2}}=NCC(x, y)
$$

数学知识
Jensen inequality 詹森不等式

$$
\sqrt[n]{\prod_{k=1}^{n} a_{k} \leq \frac{\sum_{k=1}^{n} a_{k}}{n}}
$$

示例：
$$
\frac{I(x+i, y+j)+T(i, j)}{2} \geq \sqrt[2]{I(x+i, y+j) \cdot T(i, j)}
$$
