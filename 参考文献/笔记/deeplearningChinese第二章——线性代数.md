## 基本概念

标量（scalar）：一个单独的数

向量（vector）：一列数的表示

矩阵（matrix）：二维数组

张量（tensor）：一个数组中的元素分布在若干维坐标的规则网格中。



## 矩阵的特殊计算

在深度学习中存在的一些特殊计算有：

1.矩阵和向量相加，得到另一个矩阵。比如 
$$
\textbf{C} =\textbf{A} + b
$$
其中
$$
C_{i, j} = A_{i, j} + b_{j}
$$
意义是将矩阵的每一列元素和向量相加，被称为**广播**。

2.Hadamard乘积，也称元素对应乘积，记为$\textbf{A} \odot \textbf{B}$。

3.两个相同维数的向量的点积，可看作是矩阵乘积，记为$x^{T}y$。



## 范数

  范数在机器学习中，常被用来衡量向量的大小，它是将向量映射到非负值的函数。更严格地说，它是满足以下性质的任意函数。

- $f(\textbf{x}) = 0  \Rightarrow \textbf{x} = \textbf{0}$
- $f(\textbf{x} + \textbf{y}) \leq f(\textbf{x}) + f(\textbf{y})$
- $\forall \alpha \in \textbf{R}, f(\alpha \textbf{x}) = \alpha f(\textbf{x})$

  $L^{p}$范数定义如下：
$$
\| x \|_{p} = (\sum_{i} |x_{i}|^{p})^{\frac{1}{p}}
$$
其中$p \in \mathbb{R}, p \geq 1$。

当p的值改变时，其意义和作用也在改变。

- p=1时，$L^1$范数可以用于区分是零的元素和非零但很小的元素。
- p=2时，$L^{2}$范数被成为欧几里得范数，它表示从原点出发到向量$\textbf{x}$确定的点的欧氏距离。平方$L^2$范数更容易计算，只需要计算点积$\textbf{x}^{T}\textbf{x}$就可以。平方$L^2$范数的缺点是在原点附近的增长十分缓慢，而在某些机器学习应用中，区分是零的元素和非零但很小的元素是非常重要的。
- p=$\infty$时，$L^\infty$被称为最大范数，这个范数表示向量中具有最大幅度的元素的绝对值，即$\|x\|_{\infty}=\max\limits_{i}|x_{i}|$。

在深度学习中，可以使用Frobenius范数来衡量矩阵的大小。
$$
\|\textbf{A}\|_{F} = \sqrt{\sum_{i,j}A^2_{i,j}}
$$
两个向量的点积可以使用范数来表示，即$\textbf{x}^{T}\textbf{y} = \|\textbf{x}\|_{2} \|\textbf{y}\|_{2}cos\theta$，其中$\theta$是两个向量的夹角。

