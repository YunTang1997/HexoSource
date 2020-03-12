---
title: 利用归结原理求解问题
date: 2020-03-08 11:18:11
tags: AI
categories: 人工智能
thumbnail: false
comments: true
toc: true
disqusId: ccyhweb
---


## 求解问题的步骤

(1) 已知前提$F$用谓词公式表示并化为子句集$S$
(2) 把待求解的问题$Q$用谓词公式表示，并否定$Q$,在与$ANSWER$构成析取式$(\neg Q \vee ANSWER)$;
(3) 把$(\neg Q \vee ANSWER)$化为子句，并入到子句集$S$中，得到子句集$S'$;
(4) 对子句集$S'$应用归结原理进行归结；
(5) 若得到归结式 $ANSWER$, 则答案就在$ANSWER$中。

<!-- more -->

---
### 例子：
(1) 已知：
$F_1$: 王先生（Wang）是小李（Li）的老师
$F_2$: 小李与小张（Zhang）是同班同学
$F_3$: 如果 x 与 y 是同班同学，则 x 的老师也是 y 的老师。
求：小张的老师是谁？

解：定义谓词
$T(x,y)$: x 是 y 的老师
$C(x,y)$: x 和 y 是同学
把已知前提表达成谓词公式：
$F_1:T(Wang,Li)$
$F_2:C(Li,Zhang)$
$F_3:\forall x\forall y\forall z(C(x,y)\wedge T(z,x)\rightarrow T(z,y))$
设$x$为小张的老师，把目标表示成谓词公式，并把它否定后与$ANSWER$析取：
$$
\color{red}{\neg} \exists xT(x,Zhang) \vee ANSWER(x)
$$
把上述公式化为子句集：
$C_1:T(Wang,Li)$
$C_2:C(Li,Zhang)$
$C_3:\neg C(x,y)\vee \neg T(z,x)\vee T(z,y)$
$C_4:\neg T(u,Zhang)\vee ANSWER(u)$

应用归结原理进行归结：
$C_{13}: \neg C(Li,y)\vee T(Wang,y)$
$C_{134}: \neg C(Li,Zhang)\vee ANSWER(Wang)$
$C_{1234}: ANSWER(Wang)$
故小张的老师是王老师。

<center>
![](https://hexoblog-1257022783.cos.ap-chengdu.myqcloud.com/%E5%88%A9%E7%94%A8%E5%BD%92%E7%BB%93%E5%8E%9F%E7%90%86%E6%B1%82%E8%A7%A3%E9%97%AE%E9%A2%98/20200308032354633.png)
</center>