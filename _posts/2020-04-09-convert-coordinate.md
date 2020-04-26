---
layout: post
title:  "左右手坐标系间的变换"
date:   2020-04-09 21:38:05 +0800
categories: 计算机视觉
tag: SLAM
---

* content
{:toc}

左右手坐标系下的变换只需要反转任一坐标轴就可以。以反转$z$轴为例：
## 点
\\(alpha\\)手坐标系下点（或向量）$P(x,y,z)$变换到$\beta$手坐标系下，只需要反转$z$轴$P'(x,y,-z)$，即可以乘以矩阵
$$S= \left|
\begin{array}{c}
1&0&0\\
0&1&0\\
0&0&-1
\end{array}
\right|$$。

## 旋转
$\alpha$手坐标系下的旋转矩阵$R$、点\\(P\\),在当前$\alpha$系下的变换 $P'=RP$ ，若是 $\beta$ 手坐标下的点$Q$想要感受$R$一下，就需要将$R$变换到 $\beta$ 坐标系下,但此时可以不用变换$R$ ，而是将$Q$变换到$\alpha$系下和$R$作用一下再回来，即$Q'=SRSQ$，$\beta$下的$R'=SRS$。

[参见](https://github.com/ichangjian/ichangjian.github.io/blob/master/paper/left-handed_to_right-handed.pdf)