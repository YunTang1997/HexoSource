---
title: 命题逻辑基础
date: 2020-03-05 12:09:20
tags: discretemathematics
categories: Mathematics
thumbnail: false
comments: true
toc: true
disqusId: ccyhweb
---

---
> 本文旨在让你快速了解离散数学命题逻辑的基础

## 命题
**命题：**能判断真假的陈述句
* 命题常量：$p$：小明是个男生(已指定了命题)
* 命题变量：$p$：（未指定命题）

**真值：**真，假
**命题分类：**真命题、假命题、简单命题(原子命题)、复合命题
**命题公式：**
* 重言式：真值恒为 1 （永真式）
* 矛盾式：真值恒为 0 （永假式）
* 可满足式：不是矛盾式的都是

## 命题逻辑中的基本联结词
$\neg$ : 否定（非）
$\wedge$ : 合取（与）
$\vee$ : 析取（或）
$\rightarrow$ : 蕴含（if ... then ...）
$\leftrightarrow$: 等价(当且仅当)

### 真值表：
与或非的简单真值表就不再赘述了，主要看蕴含和等价

$p \qquad q$ | $p\rightarrow q$ | $p\leftrightarrow q$  
-|-|-|-
 0 $\qquad$ 0 | 1 | 1
 0 $\qquad$ 1 | 1 | 0
 1 $\qquad$ 0 | 0 | 0
 1 $\qquad$ 1 | 1  | 1
 
例：判断公式$p\wedge r \wedge \neg(q\rightarrow p)$的类型（真值表法）

$p \quad q \quad r$ | $p\wedge r$ | $p\rightarrow q$ | $\neg(q\rightarrow p)$ | $p\wedge r\wedge \neg(q\rightarrow p)$  
-|-|-|-|-
 $0 \quad 0 \quad 0$ | 0 | 1 | 0 | 0
 $0 \quad 0 \quad 1$ | 0 | 1 | 0 | 0
 $0 \quad 1 \quad 0$ | 0 | 0 | 1 | 0
 $0 \quad 1 \quad 1$ | 0 | 0 | 1 | 0
 $1 \quad 0 \quad 0$ | 0 | 1 | 0 | 0
 $1 \quad 0 \quad 1$ | 1 | 1 | 0 | 0
 $1 \quad 1 \quad 0$ | 0 | 1 | 0 | 0
 $1 \quad 1 \quad 1$ | 1 | 1 | 0 | 0
故该式为矛盾式（永假式）
例0：求公式 $(\neg p \wedge q)\rightarrow \neg r$的成真赋值和成假赋值（同上，真值表法）

## 命题逻辑的等值演算
**等值式：**若$A\leftrightarrow B$是重言式，则可称A和B等值，记作$A<=>B$，读作`逻辑等价于`
**基本等值式：**
* 交换律：$A\vee B <=> B\vee A; A\wedge B <=> B\wedge A$
* 结合律：$(A\vee B)\vee C <=> A\vee (B\vee C)$
* 分配律：$A\vee (B\wedge C)<=>(A\vee B)\wedge (A\vee C)$
* 双重否定律：$\neg\neg A <=> A$
* 等幂律：$A<=>A\vee A;A<=>A\wedge A$
* 摩根律：$\neg (A\vee B)<=>\neg A \wedge \neg B;\neg(A\wedge B)<=>\neg A\vee \neg B$
* 吸收律：$A\vee (A\wedge B)<=>A;A\wedge (A\vee B)<=>A$
* 同一律：$A\vee 0<=>A; A\wedge 1 <=> A$
* 零律：$A\vee 1 <=> 1;A\wedge 0<=>0$
* 排中律：$A\vee \neg A<=>1$
* 矛盾律：$A\wedge \neg A<=>0$
* **蕴含等值式**：$A \rightarrow B <=> \neg A\vee B$，若A则B为真，则非A和B二者肯定有一个字真的
* **等价等值式**：$A\leftrightarrow B<=>(A\rightarrow B)\wedge (B\rightarrow A)$ 
* 假言易位式：$A\rightarrow B <=> \neg B\rightarrow \neg A$,即逆否命题
* 等价否定等值式：$A \leftrightarrow B <=> \neg A \leftrightarrow \neg B$
* 归谬论：$(A\rightarrow B)\wedge (A\rightarrow \neg B)<=>\neg A$

牢记上述基本等值式，以用来进行对复杂等值式的等值演算，比如现在我们用上述公式来证明一下归谬论：
> 
$$(A\rightarrow B)\wedge (A\rightarrow \neg B)<=>\neg A$$
左边 $=(A\rightarrow B)\wedge (A\rightarrow \neg B)$
$<=> \neg A\vee B\wedge (\neg A\vee \neg B)$ &emsp;利用蕴含等值式得到
$<=> \neg A \vee ((B\wedge \neg A)\vee (B\wedge \neg B))$ &emsp;利用分配律得到
$<=> \neg A\vee (B\wedge \neg A)$ &emsp;利用矛盾律得到
$<=> \neg A = $右边  &emsp;利用吸收律得到
思路： 用等值式去掉$\rightarrow,\leftrightarrow$ 联结词，换成只含有$\neg ,\vee ,\wedge$的尽量简洁的式子。

## 析取范式、合取范式

$def1:$ $p$ 为任意命题变量，则 $p$ 和 $\neg p$ 称为`文字`
$def2:$ 有限个文字的析取称为析取式；有限个文字的合取称为合取式
$def3:$ 
* 有限个合取式的析取称为析取范式，如$(p_1\wedge q_1)\vee(p_2\wedge q_2)\vee ... \vee(p_n\wedge q_n)$; 
* 有限个析取式的合取称为合取范式，如$(p_1\vee q_1)\wedge(p_2\vee q_2)\wedge ... \wedge(p_n\vee q_n)$;

## 主析取范式、主合取范式
$def1:$ 含有$n$个命题变量的 **合取式** $G(p_1,p_2,...,p_n)$若每个 $p_i$ 和 $\neg p_i$ 出现且仅出现一次，而且出现次序与 $p_1,p_2,...,p_n$ 的次序保持一致，则称该式 $G(p_1,p_2,...,p_n)$ 为一个**小项**。而对于一个**析取范式** $A_1 \vee A_2 \vee ... \vee A_n$, 若其中的每一个合取范式 $A_i$ 都是**小项**，则称该析取范式为**主析取范式**。

$def2:$ 含有$n$个命题变量的 **析取式** $G(p_1,p_2,...,p_n)$若每个 $p_i$ 和 $\neg p_i$ 出现且仅出现一次，而且出现次序与 $p_1,p_2,...,p_n$ 的次序保持一致，则称该式 $G(p_1,p_2,...,p_n)$ 为一个**大项**。而对于一个**合取范式** $A_1 \wedge A_2 \wedge ... \wedge A_n$, 若其中的每一个析取范式 $A_i$ 都是**大项**，则称该析取范式为**主合取范式**。
**结合例子来学习上述定义：**

例1：求 $p \rightarrow q$ 的主合取范式和主析取范式
> 法一：真值表法（不妨先求主析取）
> 1. 先写小项
> 2. 写小项的成真赋值
> 3. 找出使$p\rightarrow q$为真的小项，将它们析取
> 同理若求主合取则先写大项，写大项的成假赋值，找出使$p\rightarrow q$为假的小项，将它们合取
> 
小项 | 成真赋值 |  $p\rightarrow q$ | 是否为真  
-|-|-|-
$\neg p\wedge \neg q$ | $0 \qquad 0$ | 1 | 是
$\neg p\wedge q$ | $0 \qquad 1$ | 1 | 是
$p\wedge \neg q$ | $1 \qquad 0$ | 0 | 否
$p\wedge q$ | $1 \qquad 1$ | 1  | 是
故主析取范式为：
$$
p\rightarrow q <=> (\neg p\wedge \neg q)\vee (\neg p\wedge q)\vee ( p\wedge q)
$$
主合取范式为：(找$p\rightarrow q$为假时的小项对应的大项再将它们合取)
$$
p\rightarrow q <=> \neg p \vee q
$$
法二：等值演算法(常用)
左边$ = p\rightarrow q$
$<=> \neg p \vee q$ 主合取范式（蕴含等值式）
$<=> (\neg p \wedge \color{red}{(q\vee \neg q)})\vee (\color{red}{(p \vee \neg p)}\wedge q)$ (由排中律构造)
$<=> \color{green}{(\neg p \wedge q)}\vee(\neg p \wedge \neg q)\vee( p \wedge q)\vee \color{green}{(\neg p \wedge q)}$
$<=> \color{green}{(\neg p \wedge q)}\vee(\neg p \wedge \neg q)\vee( p \wedge q)$ 主析取范式(幂等律)

再看一个稍微复杂点的例子
例2：求 $p \rightarrow ((p\rightarrow q)\wedge \neg (\neg q \vee \neg p))$ 的主合取范式
$proof:$
左边$ =p \rightarrow ((p\rightarrow q)\wedge \neg (\neg q \vee \neg p))$
$<=> \neg p \vee ((\neg p \vee q)\wedge (q\wedge p))$ (蕴含等价)
$<=> (\neg p \vee(\neg p \vee q))\wedge (\neg p \vee (q \wedge p))$
$<=> (\neg p \vee q)\wedge (\neg p \vee q)\wedge (\neg p \vee p)$(摩根律)
$<=> (\neg p \vee q)\wedge (\neg p \vee q)<=>(\neg p \vee q)$ 主合取式(等幂律)

---
## 联结词的完备集 $(\neg \vee \wedge \rightarrow \leftrightarrow)$
$def:$ $S$ 是一个联结词集合，若任意一个命题公式都可以由 $S$ 中的额联结词表示出来且命题公式与之等价，则称 $S$ 为一个联结词的**完备集**。
$Th:$ 以下联结词的集合都是一个联结词完备集：
* $S_1 = \{ \neg, \vee, \wedge \}$
* $S_2 = \{ \neg, \vee, \wedge, \rightarrow \}$
* $S_3 = \{ \neg, \vee, \wedge, \rightarrow, \leftrightarrow \}$
* $S_4 = \{ \neg, \wedge \}$
* $S_5 = \{ \neg, \vee \}$
* $S_6 = \{ \neg, \rightarrow \}$
* $S_7 = \{ \uparrow \}$ 与非 $p \uparrow q <=> \neg(p\wedge q)$
* $S_8 = \{ \downarrow \}$ 或非 $p \downarrow q <=> \neg(p \vee q)$

来看一个对应知识的例题
例3：将 $p\rightarrow q$ 分别化成上述 $S_4,S_5,S_7,S_8$ 集合上的公式
$Proof:$
$p\rightarrow q <=> \neg p \vee q$  ---------------------------------$S_5$
$<=> \neg\neg(\neg p \vee q)<=> \neg(p \wedge \neg q)$------$S_4$
$<=> p\uparrow \neg q<=>p\uparrow(\neg q\vee \neg q)<=>p\uparrow\neg(q\wedge q)<=>p\uparrow(q\uparrow q)$-----$S_7$
$p\rightarrow q<=>\neg\neg(\neg p\vee q)<=>\neg(\neg p\downarrow q)<=>\neg(p\downarrow p\downarrow q)$
$<=>(p\downarrow p\downarrow q)\downarrow(p\downarrow p\downarrow q)$---$S_8$

---
待续。。。