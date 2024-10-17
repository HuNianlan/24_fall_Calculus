---
marp: true
math: mathjax
---

# GEMA1001 Week 5 Tutorial

HuNianlan

---
### Note：10.24 quiz 1 
- 45min 
- 3道题
- 难度相当于考试中的第一、二道大题
---
## Contents

### Review
- 上（下）确界
- 数列及其单调性、有界性
- 数列的极限
- 极限证明技巧举例
- 数列极限的性质及运算法则
- 单调有界数列极限存在准则
- 区间套定理与凝聚定理
- 极限计算举例
---
**定义 1.1** 我们说一个集合 $E$ 是 *数集* 如果它是 $\mathbb{R}$ 中的子集.

---

**定义 1.2** 给定一个非空集合 $E \subseteq \mathbb{R}$

1. 如 $\exists\,M\in\mathbb{R}$, 使得 $\forall\,x\in E$，有 $x\leq M$，则称 $E$ 是有 *上界的（bounded above）*，且称 $M$ 是 $E$ 的一个 *上界（upper bound）*；
2. 如 $\exists\,m\in\mathbb{R}$, 使得 $\forall\,x\in E$，有 $x\geq m$，则称 $E$ 是有 *下界的（lower bounded）*，且称 $m$ 是 $E$ 的一个 *下界（lower bound）*；
3. 若 $E$ 同时有上界和下界，则称 $E$ 为 *有界（bounded）*，反之，则称 $E$ 是 *无界（unbounded）* 的. 换言之，$\exists\,\overline{M}>0$，使得 $\forall\,x\in E$，有 $|x|\leq \overline{M}$，此时称 $\overline{M}$ 为数集 $E$ 的一个 *界（bound）*.

---

**定义 1.3** 给定非空数集 $E \subseteq \mathbb{R}$，若 $\exists \beta \in \mathbb{R}$ 满足

1. $\forall\,x\in E$，有 $x \leq \beta$，即 $\beta$ 是 $E$ 的一个 *上界*；
2. $\forall\epsilon>0,\,\exists\,x_{\epsilon}\in E$，使得 $x_{\epsilon} > \beta - \epsilon$，即 $\beta$ 是 $E$ 所有上界中最小的一个上界.

则称 $\beta$ 是 $E$ 的 *上确界（supremum）*，记为 $\beta = \sup E$.

---

**定义 1.3$^{\prime}$** 若非空数集 $E$ 有下界，则其下界 $\alpha \in \mathbb{R}$ 称为 $E$ 的 *下确界* 当且仅当任何大于 $\alpha$ 的数不再是 $E$ 的下界，即 $\forall \epsilon > 0, \exists x_{\epsilon} \in E$，使得 $x_{\epsilon} < \alpha + \epsilon$. 记为 $\alpha = \inf E$.

---
**定义 2.1** 一个*数列（sequence）* $\{x_{n}\}_{n=1}^{\infty}$ 是正整数集 $\mathbb{Z}_{>0}$ 上的函数，即映射
\[
\mathbb{Z}_{\geq 0} \longrightarrow \mathbb{R} \quad n \longmapsto x_{n}
\]
其中 $x_{n}$ 称为该数列的 *通项或一般项（general term）*. 在这个数列中，第一项是 $x_{1}$，第二项是 $x_{2}$，$\cdots$，第 $n$ 项是 $x_{n}$ 等等. 常将 $\{x_{n}\}_{n=1}^{\infty}$ 简写为 $\{x_{n}\}$.

有时，我们也考虑 *常数列（constant sequence）*，即每一项都是常数 $C$ 的数列.


---

**定义 2.2** 若数列 $\{x_{n}\}$ 满足 $\forall\,n$，有 $x_{n+1} \geq x_{n}$（或 $x_{n+1} > x_{n}$），则称 $\{x_{n}\}$ 是 *单调增加（严格单调增加）数列*；反之，若 $\forall n$，有 $x_{n+1} \leq x_{n}$（或 $x_{n+1} < x_{n}$），则称 $\{x_{n}\}$ 是 *单调减少（严格单调减少）数列.*

---

**定义 2.3** 若数列 $\{x_{n}\}$ 满足：$\exists\,M > 0$ 使得 $\forall n$，都有 $|x_{n}| \leq M$，则称 $\{x_{n}\}$ 是 *有界数列*. 类似地，可给出 *上（下）界* 的定义.

---
**定义 3.1** 对数列 $\{x_{n}\}$，若 $\exists$ 数 $A$，$\forall \epsilon > 0,\, \exists\, N \in \mathbb{N}$，使得当 $n > N$ 时，有 $|x_{n} - A| < \epsilon$，则称 $\{x_{n}\}$ 的 *极限*（limit）为 $A$，或称数列 $\{x_{n}\}$ *收敛*（convergent），且 *收敛于*（convergent to） $A$，记为 $\lim\limits_{n\to\infty}\,x_{n} = A$（或者 $x_{n} \to A\,(n \to \infty)$）. 若不存在这样的常数 $A$，则称数列 $\{x_{n}\}$无极限，也称其 *发散*（divergent）或不收敛.

---
**定义 3.2** 极限为 $0$ 的数列 $\{x_{n}\}$ 称为 *无穷小量*（infinitesimal），简称 $x_{n}$ 为 *无穷小*（infinite small）.

---

**定义 3.3** 对数列 $\{x_{n}\}$，若 $\forall G > 0,\, \exists N \in \mathbb{N}$，使得当 $n > N$ 时，$|x_{n}| > G$，则称 $\{x_{n}\}$ 是 *无穷大量*，简称 $x_{n}$ 为 *无穷大*，记为 $\lim\limits_{n \to \infty} = \infty$.

---

**定义 6.1** 设 $\{n_{1}, n_{2}, \cdots\}$ 是正整数集的一个无穷子集，且 $n_{k+1} > n_{k}, k = 1, 2, \cdots$，则数列 $\{x_{n_{k}}\}_{k=1}^{\infty}$ 称为 $\{x_{n}\}$ 的一个 *子数列（sub-sequence）*，简称 *子列*.

---

**定义 7.1** 一列 **闭** 区间 $\{[a_{n}, b_{n}]\}$ 称为是一个 *闭区间套*，如果
1. $[a_{n+1},\,b_{n+1}] \subseteq [a_{n},\,b_{n}],\,n=1,2,3,\cdots$
2. $\lim\limits_{n\to\infty}\,(b_{n}-a_{n})=0$.
