# 期中复习
## 第一章 集合
### 1. 基本概念
- 幂集$P(A), 2^A$
  - **设$A$为集合，称$A$的全体子集构成的集合为$A$的幂集**
  - $P(A)=\lbrace X \mid X \\subseteq A \rbrace$
  - 如果$A$是$n$元集，$P(A)$有$2^n$个元素
- 对称差$A \oplus B$
  - **$A \oplus B = (A-B)\cup (B-A)$**
- 广义并$\cup \mathcal{A}$
  - **设$\mathcal{A}$为一个集族，$\mathcal{A}$中全体元素的元素组成的集合称为$\mathcal{A}$的广义并**
  - $\cup \mathcal{A} = \lbrace x \mid \exists A \in \mathcal{A}\ s.t.\ x \in A \rbrace$
  - $\cup \varnothing  = \varnothing$
- 广义交$\cap \mathcal{A}$
  - **设$\mathcal{A}$为一个集族，$\mathcal{A}$中全体元素的公共元素组成的集合称为$\mathcal{A}$的广义交**
  - $\cap \mathcal{A} = \lbrace x\mid \forall A \in \mathcal{A}, x\in A\rbrace$
  - $\cap \varnothing  = E$

### 2. 运算性质
- *一般都可以画图得出，略*

### 3. 有穷集的计数
- 包含排斥原理：

$$
\vert A_1 \cup A_2 \cup ... \cup A_n \vert = \sum_{i=1}^{n}\vert A_i\vert - \sum_{1\leq i <j \leq n}\vert A_i \cap A_j \vert +\sum_{1\leq i < j < k \leq n}\vert A_i \cap A_j \cap A_k \vert +... + (-1)^{n-1}\vert A_1 \cap A_2 \cap ...\cap A_n\vert
$$

  - 例题：错排问题
    - *在概统复习里写过了*

## 第二章 二元关系
### 1. 基本概念
- 有序对$\langle x,y\rangle$
  - **$\langle x,y\rangle  \neq \langle y,x\rangle$**
- 笛卡尔积$A \times B$
  - **$A \times B = \lbrace \langle x,y\rangle \mid x \in A \wedge y \in B \rbrace$**
  - 不满足交换律与结合律；对并与交满足分配律
- 二元关系$R$
  - 如果一个集合满足以下条件之一，称为二元关系
    - 集合非空，元素都是有序对
    - 集合为空
  - 若$\langle x,y\rangle  \in R$，记作$xRy$，其中$R$为从$A$到$B$的二元关系；若$A=B$，称为$A$上的二元关系
  - 特殊的二元关系
    - 全域关系$E_A = A\times A$
    - 恒等关系$I_A = \lbrace \langle x,x\rangle \mid x \in A\rbrace$
    - 包含关系、小于等于关系、整除关系...
  - 关系矩阵$\mathbf{M}_R$
    - $r_{ij} = 1$，若$x_i R y_j$
    - $r_{ij} = 1$，否则
  - 关系图$G_R$：每一对有序对对应一条有向边

### 2. 关系的运算
- 定义域$domR$
  - **$R$中所有第一元素构成的集合**
- 值域$ranR$
  - **$R$中所有第二元素构成的集合**
- 域$fldR$
  - **$fldR = domR \cup ranR$**
- 逆关系$R^{-1}$
  - **$R^{-1} = \lbrace \langle x,y\rangle \mid \lbrace y,x\rbrace \in R \rbrace$**
  - $(F^{-1})^{-1} = F$
  - $domF^{-1} = ranF, ranF^{-1} = domF$
- $F$和$G$的复合$F\circ G$
  - **$F\circ G = \lbrace \langle x,z\rangle \mid \exists y\ s.t.\ \langle x,y\rangle \in F, \langle y,z\rangle \in G\rbrace$**
  - $(F\circ G)\circ H = F\circ (G\circ H)$
  - $(F\circ G)^{-1} = G^{-1} \circ F^{-1}$
  - $F\circ (G\cup H) = F\circ G \cup F\circ H$
  - $(G\cup H) \circ F = G\circ F \cup H\circ F$
  - $F\circ (G\cap H) \subseteq F\circ G \cap F\circ H$ *（试想$G\cap H$为空集的情形）*
  - $(G\cap H) \circ F \subseteq G\circ F \cap H\circ F$
- $R$在$A$上的限制$R\upharpoonright A$
  - **$R\upharpoonright A = \lbrace \langle x,y\rangle \mid \langle x,y\rangle \in R, x \in A \rbrace$**
  - $F\upharpoonright (A\cup B) = F\upharpoonright A \cup F\upharpoonright B$
  - $F\upharpoonright (A\cap B) = F\upharpoonright A \cap F\upharpoonright B$
- $A$在$R$上的像$R[A]$
  - **$R[A] = ran(R\upharpoonright A)$**
  - $F[A\cup B] = F[A] \cup F[B]$
  - $F[A\cap B] = F[A] \cap F[B]$
- $R$的$n$次幂$R^n$
  - **$R^n = R^{n-1}\circ R,R^0 = I_A$**
  - $R^n$的关系矩阵是$\mathbf{M} ^n$，其中的相加是逻辑加
  - 设$A$为$n$元集，$R$是$A$上的关系，则存在不相等的自然数$s,t\ s.t.\ R^s = R^t$
    - 证明：$A$上关系的总数$\vert P(A\times A)\vert = 2^{n^2}$是有限的，由抽屉原理存在相等
    - $R^s = R^t$，则：
      - $\forall k \in \mathbb{N} , R^{s+k} = R^{t+k}$
      - $\forall k,i \in \mathbb{N} , R^{s+kp+i} = R^{s+i},p = t -s$
      - 令$S=\lbrace R^0,R^1,...,R^{t-1}\rbrace$，则$\forall q \in \mathbb{N}, R^q \in S$
  - $R^m\circ R^n = R^{m+n}$
    - 对$n$归纳证明
  - $(R^m)^n = R^{mn}$
    - 由上一条性质归纳导出

### 3. 关系的性质
- 自反关系：$\forall x \in A\rightarrow \langle x,x\rangle \in R$
  - 当且仅当$I_A \subseteq R$
  - 关系矩阵：主对角元全为$1$
  - 关系图：每个顶点都有环
- 反自反关系：$\forall x \in A\rightarrow  \langle x,x\rangle \notin R$
  - 当且仅当$R\cap I_A = \\varnothing$
  - 关系矩阵：主对角元全为$0$
  - 关系图：每个顶点都无环
- 对称关系：$\forall \langle x,y\rangle \in R\rightarrow  \langle y,x\rangle \in R$
  - 当且仅当$R = R^{-1}$
  - 关系矩阵：对称矩阵
  - 关系图：无单边
- 反对称关系：$\langle x,y\rangle \in R\wedge  \langle y,x\rangle \in R \rightarrow  x=y$
  - 当且仅当$R\cap R^{-1} \subseteq I_A$
  - $r_{ij} = 1 \wedge i\neq j \rightarrow r_{ji}=0$
  - 关系图：无双向边
- 传递关系：$\forall \langle x,y\rangle \in R\wedge \langle y,z\rangle \in R\rightarrow \langle x,z\rangle \in R$
  - 当且仅当$R \circ R \subseteq R$
  - $\mathbf{M} ^2$中$1$所在的位置，$\mathbf{M}$中都是$1$
  - 关系图：若$x_i$到$x_j$有边且$x_j$到$x_k$有边，则$x_i$到$x_k$有边

### 4. 关系的闭包
- 自反（对称/传递）闭包$R'$满足以下条件：
  - $R'$是自反（对称/传递）的
  - $R\subseteq R'$
  - 对$A$上任何自反（对称/传递）关系$R''$，均有$R'\subseteq R''$
- 自反闭包
  - $r(R) = R \cup R^0$
  - $\mathbf{M}_r  = \mathbf{M} + E$
- 对称闭包
  - $s(R) = R \cup R^{-1}$
  - $\mathbf{M}_s  = \mathbf{M} + \mathbf{M}'$
- 传递闭包
  - $t(R) = R \cup R^2 \cup R^3 \cup ...$
  - $\mathbf{M}_t  = \mathbf{M} + \mathbf{M}^2 + \mathbf{M}^3 + ...$
  - 设$R$为有穷集$A$上的关系，则存在正整数$r$使得$t(R) = R \cup R^2 \cup ... \cup R^r$
  - 沃舍尔算法
    - 暂略
- 关系性质与闭包运算的关系
  - $s,t$保持自反性
  - $r,t$保持对称性
  - $r$保持传递性，$s$不保持传递性
    - 考虑只有一条边的关系图，其对称闭包为双向边，无环，无传递性
- $tsr(R) = t(s(r(R)))$
  - 计算自反、对称、传递闭包时，为了不失去传递性，$t$应当在$s$后

### 5. 等价关系与划分
- **等价关系：自反、对称、传递的关系**
  - $R$是一个等价关系，若$\langle x,y\rangle \in R$，则称$x$等价于$y$，记作$x\sim y$
  - 常见的等价关系：模运算
  - *以等价关系的视角看哈希算法，在做ics题的时候很方便*
- **关于$R$的等价类**$[x]_R,[x],\overline{x}$
  - 设$R$为$A$上的等价关系，$\forall x \in A$，令

$$
    [x]_R = \lbrace y \mid y \in A, \langle x,y\rangle \in R \rbrace
$$

- 商集$A/R$
  - **以$R$的所有等价类作为元素的集合称为$A$对$R$的商集**

$$
    A/R = \lbrace [x]_R \mid x \in A \rbrace
$$

- 划分$\pi $
  - 设$A$为非空集合，若$A$的子集族$\pi \subseteq P(A)$满足以下条件，则称为$A$的一个划分
    - $\varnothing \notin \pi$
    - $\forall X,Y \in \pi, X \neq Y \rightarrow X\cap Y = \varnothing$
    - $\cup \pi = A$
  - 即元素集合无公共元素且包含所有元素的子集族
  - **商集就是$A$的一个划分，等价关系与商集一一对应，故等价关系与划分一一对应**

### 6. 偏序关系
- **偏序关系：自反、反对称、传递的关系**
- 设$\leqslant$为偏序关系，若$\langle x,y\rangle \in \leqslant$，则记作$x \leqslant y$，读作$x$小于等于$y$，这里的小于是指在偏序中$x$在$y$的前面
- 在偏序关系$\leqslant$的集合$A$中任取两个元素$x,y$，有下列情况：
  - $x < y \Vert y < x$
  - $x = y$
  - $x$与$y$不可比
- $A$和$A$上的偏序关系$\leqslant$一起称作偏序集$\langle A,\leqslant\rangle$
- $y$覆盖$x$：$x < y$且不存在$z$使得$x < z < y$
- 哈斯图：若$x< y$，将$x$画在$y$下方；若$y$覆盖$x$，连接$x,y$
- 最小元、最大元、极小元、极大元
  - 设$\langle A,\leqslant\rangle$为偏序集，$B\subseteq A, y \in B$
    - 若$\forall x \in B, y \leqslant x$，则称$y$是$B$的最小元
    - 若$\forall x \in B, x \leqslant y$，则称$y$是$B$的最大元
    - 若$\forall x \in B, x \leqslant y \rightarrow x = y$，则称$y$是$B$的极大元
    - 若$\forall x \in B, y \leqslant x \rightarrow x = y$，则称$y$是$B$的极小元
  - 最小元与其他元素都可比；而极小元与其他元素不一定可比，只要没有比它小的元素，就是极小元
  - **有穷集**中极小元一定存在；最小元不一定存在
  - 极小元可能有多个；最小元若存在则唯一
  - 如果极小元唯一，则为最小元
  - 哈斯图中的孤立点既是极小元也是极大元
- 上界、下界、最小上界、最大下界
  - 设$\langle A,\leqslant\rangle$为偏序集，$B\subseteq A, y \in A$
    - *$y \in A$不一定$y \in B$，这与最大最小元不同*
    - 若$\forall x \in B, x \leqslant y$，则称$y$是$B$的上界
    - 若$\forall x \in B, y \leqslant x$，则称$y$是$B$的下界
    - 令$C = \lbrace y \mid y\text{为}B\text{的上界}\rbrace$，则称$C$中最小元为$B$的最小上界
    - 令$C = \lbrace y \mid y\text{为}B\text{的下界}\rbrace$，则称$C$中最大元为$B$的最大下界
  - $B$的上界、下界、最小上界、最大下界都可能不存在；如果存在，最小上界和最大下界是唯一的

## 第三章 函数
### 1. 函数的定义与性质
- **函数是一种特殊的二元关系**
  - 设$F$为二元关系，若$\forall x \in domF$都存在唯一的$y\in ranF$使$xFy$成立，则称$F$为函数，若有$xFy$，则记作$y=F(x)$
    - *$\langle 1, 2\rangle \langle 1,3\rangle$不是函数，没有单值性*
  - 用集合相等来定义函数相等；若两个函数$F$和$G$相等，则满足
    - $domF = domG$
    - $\forall x \in domF = domG, F(x) = G(x)$
- 所有从$A$到$B$的函数的集合记作$B^A$
  - $\vert B^A \vert = \vert B \vert ^ {\vert A \vert}$
  - $\varnothing ^\varnothing = \lbrace \varnothing \rbrace$ *（这里$\varnothing:\varnothing \rightarrow \varnothing$）*
  - $B ^\varnothing = \lbrace \varnothing \rbrace$ *（这里$\varnothing:\varnothing \rightarrow B$）*
  - $\varnothing ^A = \varnothing$ *（这里$\varnothing$表示不存在这样的函数）*

$$
    B^A = \lbrace f \mid f:A \rightarrow B \rbrace
$$

- 设函数$f:A\rightarrow B,A_1\subseteq A, B_1 \subseteq B$
  - $A_1$在$f$下的**像**$f(A_1) = \lbrace f(x)\mid x \in A_1\rbrace$
  - $B_1$在$f$下的**原像**$f^{-1}(B_1) = \lbrace x \in A \mid f(x) \in B_1\rbrace$
  - $A_1 \subseteq f^{-1}(f(A_1))$ *可能有多个$x$对应一个$y$*
- 设$f:A \rightarrow B$
  - 若$ranf = B$，则称$f:A\rightarrow B$是**满射**
  - 若$\forall y \in ranf$都存在唯一的$x \in A$使得$f(x) = y$，则称$f:A\rightarrow B$是**单射**
  - 若$f:A\rightarrow B$既是满射又是单射，则称$f:A\rightarrow B$是**双射**
    - $P(A)$和$\lbrace 0, 1\rbrace^A$存在双射，用$0,1$来表示是否选择该元素作为元素子集的元素
    - $\mathbb{Z} \rightarrow \mathbb{N}$的双射：负数对应奇数，正数对应偶数，零对应零
      - $f(x) = 2x, x \geq 0$
      - $f(x) = -2x-1, x < 0$
- 常用函数
  - 常函数、恒等函数、单调递增（减）函数（定义于一般的偏序集上）、特征函数$\chi_{A'}:A\rightarrow \lbrace 0,1\rbrace\$（用$0,1$表示$A$中元素是否在子集$A'$中）
  - 自然映射$g:A\rightarrow A/R,g(a)=[a],\forall a \in A$
    - 即映到等价类 
  - 阶
    - 暂略，见书p50

### 2. 函数的复合与反函数
- **函数的复合是关系的右复合**

$$
    F\circ G(x) = G(F(x))
$$

- 两个函数都为满射/单射/双射时，复合保持满射/单射/双射；逆命题不为真
  - 考虑单射$f:A\rightarrow B$和单射$f\circ g:A \rightarrow C$，$g:B \rightarrow C$不为单射
  
$$ 
\begin{align*}
  f &= \lbrace \langle a_1,b_1\rangle,\langle a_2,b_2\rangle,\langle a_3,b_3\rangle\rbrace \\
  g &= \lbrace \langle b_1,c_1\rangle,\langle b_2,c_2\rangle,\langle b_3,c_3\rangle,\langle b_4,c_3\rangle\rbrace \\
  f \circ g &= \lbrace \langle a_1,c_1\rangle,\langle a_2,c_2\rangle,\langle a_3,c_3\rangle\rbrace
\end{align*}
$$

- 设$f:A\rightarrow B$是双射，则$f^{-1}:B\rightarrow A$也是双射，称其为$f$的反函数
  - $f^{-1}\circ f = I_B, f\circ f^{-1} = I_A$

### 3. 双射函数与集合的基数
- **集合的势：度量集合所含元素多少的量**
- **等势：如果存在从集合$A$到集合$B$的双射函数，则称$A$和$B$是等势的，记作$A\approx B$**
  - $\mathbb{Z} \approx \mathbb{N}$
  - $\mathbb{N}\times \mathbb{N} \approx \mathbb{N}$
    - 找到能“数遍”第一象限整数坐标点的方法
    - $f(\langle m,n\rangle) = \frac{(m+n+1)(m+n)}{2} + m$
    - *$x+y = m+n$斜线下方点的个数$+$横坐标$m$*
  - $\mathbb{N} \approx \mathbb{Q}$
    - “数遍”有理数表的方法
  - $(0,1) \approx \mathbb{R}$
    - $f:(0,1)\rightarrow \mathbb{R}, f(x) = \tan {\frac{2x-1}{2}\pi}$
  - $[0,1] \approx (0,1)$
    - 解决端点$0,1$的对应问题
    - 选择一个无限序列向后平移$2$个单位，最前两个元素空出来对应$0,1$，其余对应自身
    - $\frac{1}{2^n}$
  - $\forall a, b \in \mathbb{R}, a < b, [0,1] \approx [a,b]$
    - 一次函数即可
  - $P(A) \approx \lbrace 0, 1\rbrace ^A$
- 一般来说，等势具有自反性、对称性、传递性
  - $\mathbb{N} \approx \mathbb{Z} \approx \mathbb{Q} \approx \mathbb{N}\times \mathbb{N}$
  - $\mathbb{R} \approx [0,1] \approx (0,1)$
- **康托定理**
  - **$\mathbb{N} \not\approx \mathbb{R}$**
    - $[0,1]$间的小数不可用自然数数出，总能构造出新的小数
  - **$\forall A, A \not\approx P(A)$**
    - 设$g:A\rightarrow P(A)$
  
  $$
    B=\lbrace x \mid x \in A, x \notin g(x)\rbrace
  $$
  
  - 则$B \in P(A)$，但
  
  $$
    \forall x \in A, x \in B \Leftrightarrow x \notin g(x)
  $$
  
  - 从而$\forall x \in A, B \neq g(x)$，即$B\notin ran g$
  - $\mathbb{N} \not\approx P(\mathbb{N}),\mathbb{N} \not\approx \lbrace 0, 1 \rbrace^\mathbb{N}$
- **优势：如果存在从集合$A$到集合$B$的单射函数，则称$B$优势于$A$，记作$A\leqslant \cdot  B$**
  - 真优势：若$A\leqslant \cdot  B$且$A\neq B$，则$A <\cdot B$
  - $\mathbb{N} \leqslant \cdot \mathbb{N}$
  - $\mathbb{N} <\cdot \mathbb{R}$
  - $A <\cdot P(A)$
  - 自反性、反对称性（在等势作等价关系的意义下）、传递性
    - 其中反对称性给出一种证明等势的简单方法：分别构造两个方向的单射
    - 可用该方法结合二进制与十进制小数证明$\lbrace 0, 1 \rbrace^\mathbb{N} \approx [0,1)$
    - 故根据传递性，总结等势关系如下：
  
$$
\begin{align*}
  \mathbb{N} &\approx \mathbb{Z} \approx \mathbb{Q} \approx \mathbb{Z} \times \mathbb{Z} \\
  \mathbb{R} &\approx [a,b] \approx (c,d) \approx \lbrace 0, 1 \rbrace^\mathbb{N} \approx P(\mathbb{N}) \\
  \lbrace 0, 1 \rbrace^A &\approx P(A)\\
  \mathbb{N} &<\cdot \mathbb{R}\\
  A &<\cdot P(A)
\end{align*}
$$

- 有穷集：空集或与某个$\mathbb{N}_k = \lbrace 0, 1, ..., k-1 \rbrace$等势
- 无穷集：不是有穷的集合
- **基数$cardA, \vert A \vert$**
  - 有穷基数
    - $cardA = 0, A = \varnothing$
    - $cardA = k, A \approx \mathbb{N}_k$
  - 无穷基数
    - **$card \mathbb{N} = \aleph _0$**
    - **$card \mathbb{R} = \aleph$**
  - 集合的基数就是集合的势
  
$$
\begin{align*}
  card \mathbb{N} &=card \mathbb{Z} = card \mathbb{Q} = card \mathbb{Z} \times \mathbb{Z} = \aleph _0\\
  card \mathbb{R} &= card [a,b] = card (c,d) = card \lbrace 0, 1 \rbrace^\mathbb{N} = card P(\mathbb{N}) = \aleph\\
  \aleph _0 &< \aleph 
\end{align*}
$$

- 可数集（可列集）：$cardA \leq \aleph _0$

## 第四章 初等数论基础及其应用
### 1. 素数
- 带余除法：$a=qb+r,0\leq r \leq \vert b \vert$
- 素数与合数都在$>1$的正整数前提下定义
- 素数的性质略
- **算数基本定理（素因子分解）：**设$a>1$，则

  $$
    a = p_1^{r_1}p_2^{r_2}...p_k^{r_k}
  $$

  - 其中$p_i$是互不相同的素数，$r_i$是正整数，不计顺序的情况下分解唯一
  - 整数$d$为$a$因子的充要条件为$d$分解后素因子的幂次小于等于$a$中幂次
- 反证法可证：有无穷多个素数
- **素数定理：**
  
  $$
    \lim_{n \to +\infty}\frac{\pi(n)}{n/\ln{n}} = 1
  $$

- 素数测试
  - 合数$a$一定有小于等于$\sqrt{a}$的素因子
  - 厄拉多塞筛法：删去小素数的倍数
  
### 2. 最大公因数与最小公倍数
- 若$a \mid m, b \mid m$，则$\operatorname{lcm} (a,b) \mid m$
- 若$d \mid a, d \mid b$，则$d \mid \gcd (a,b)$
- **利用素因子分解求最大公因数和最小公倍数**
  - 最大公因数的幂次取最小值
  - 最小公倍数的幂次取最大值
- **辗转相除法求最大公因数**
  - 设$a=qb+r$，则$\gcd (a,b) = \gcd (b,r)$
  - 存在整数$x,y$使得$\gcd (a,b) = xa+yb$
    - 从后向前逐个代回辗转相除法中的步骤式
- **$a,b$互素的充要条件为存在$x,y$使得$xa+yb=1$**

### 3. 同余
- 同余是等价关系，即有自反性、对称性、传递性
- 同余性质暂略
- 同余关系下的模$m$等价类$[a]_m$
  - $[a] \oplus [b] = [a+b]$
  - $[a] \otimes [b] = [ab]$

### 4. 一次同余方程
- 设$m>0$，下列方程称作一次同余方程

$$
  ax\equiv c \pmod{m}
$$

- **方程有解的充要条件是$\gcd (a,m)\mid c$**
  - 充分性：只要证$ax \equiv \gcd (a,m) \pmod{m}$有解即可，对应系数同时乘以倍数即得到原命题
    - $a_1 = \frac{a}{\gcd (a,m)}, m_1 = \frac{m}{\gcd (a,m)}$二者互素
    - **素数性质：**$a_1 x_1 + m_1 y_1 = 1$ 
    - 两边乘以$\gcd (a,m)$，得$ax_1 + my_1 = \gcd (a,m)$
    - 取$x = x_1 \cdot \frac{c}{\gcd (a,m)}, y = y_1 \cdot \frac{c}{\gcd (a,m)}$
  - 必要性移项即可得，略
- 方程的解可以写成$x \equiv x_0\pmod{m}$的形式，只需**验证对模$m$的每个等价类的一个代表即可找出方程所有的解**
- 如果$ab \equiv 1\pmod{m}$，则称$b$为$a$的模$m$逆，记作$a^{-1}\pmod{m},a^{-1}$
  - 即为方程$ax \equiv 1 \pmod{m}$的解
  - $a$的模$m$逆存在的充要条件是$a,m$互素
  - $a$的模$m$逆若存在则唯一（在模$m$意义下）

### 5. 欧拉定理和费马小定理
- 欧拉函数$\phi$：$\phi(n)$表示$\lbrace 1, 2, ..., n\rbrace$中与$n$互素的元素个数
  - 当$n$为素数时，$\phi(n) = n-1$
  - 当$n$为合数时，$\phi(n) < n-1$
- 给定素因子分解$n = p_1^{r_1}p_2^{r_2}...p_k^{r_k}$，根据包含排斥原理（考虑为$p_i$倍数的事件），有：

$$
\begin{align*}
  \phi(n) &= n - (\frac{n}{p_1} + \frac{n}{p_2}+...+\frac{n}{p_k}) + (\frac{n}{p_1 p_2}+\frac{n}{p_2 p_3}+...+\frac{n}{p_{k-1} p_k})-...+(-1)^k\frac{n}{p_1 p_2...p_k}\\
  &= n(1-\frac{1}{p_1})(1-\frac{1}{p_2})...(1-\frac{1}{p_k})
\end{align*}
$$

- **欧拉定理：**设$a,n$互素，则

$$
  a^{\phi(n)}\equiv 1 \pmod{n}
$$

- **费马小定理：**设$p$是素数，则对任意整数$a$，

$$
  a^p \equiv a \pmod{p}
$$

- 等价命题：设$p$是素数，$a,p$互素，则

$$
  a^{p-1} \equiv 1 \pmod{p}
$$

- 应用：
  - 提供了一种不用分解因子就能确认一个数是合数的方法
  - 用于计算指数很大时的余数

## 第五章 图的基本概念
*概念实在是太多。。*
### 1. 定义及运算
- 无序积$A\&B = \lbrace \lbrace a,b\rbrace \mid a \in A, b \in B\rbrace$
  - 其中的无序对$(a,b)$
- 无向图和有向图$G = \langle V,E\rangle$，规定点集$V$为非空集
  - 区别为边集$E$的元素为无序对/有序对
  - 具体定义略
- **零图**：一条边也没有的图
  - **平凡图**：$1$阶零图
- 空图$\varnothing$：运算中产生的点集为空集的图
- 标定图/非标定图：是/否给每一个顶点和每一条边指定一个符号
- **基图**：将有向图中有向边改为无向边得到的无向图称为这个有向图的基图
- $e_k$与$v_i$的**关联次数**
  - 若$v_i$是$e_k$的一个端点，关联次数为$1$
  - 若$e_k$是$v_i$上的环，关联次数为$2$
  - $v_i$不与$e_k$关联，关联次数为$0$
  - 没有边关联的点为孤立点
  - 关联集$I_G(v) = \lbrace e \mid e \in E, e \text{与} v \text{相关联} \rbrace$
- 相邻
  - 两条边有一个公共顶点（有向图一边起点为另一边终点）
  - 两个顶点之间有一条边（有向图为有向边）
- **无向图的邻域**$N_G(v)=\lbrace u \mid u \in V,(u,v)\in E,u \neq v \rbrace$
- 有向图的后继元素$\Gamma_D^{+}(v) = \lbrace u \mid u \in V , \langle v,u\rangle \in E, u \neq v\rbrace$
- 有向图的先驱元素$\Gamma_D^{-}(v) = \lbrace u \mid u \in V , \langle u,v\rangle \in E, u \neq v\rbrace$
- **有向图的领域**$N_G(v)=\Gamma_D^{+}(v) \cup \Gamma_D^{-}(v)$
- 闭邻域$\overline{N}_G(v)=N_G(v) \cup \lbrace v \rbrace$
- 平行边（**有向图中方向相同**）
- **多重图：**含平行边的图
- **简单图：**既不含平行边也不含环的图
- 母图/子图：边集与点集都包含/被包含
  - 真子图：边集与点集都被真包含
  - **生成图：**点集相等，边集被包含
  - $G$的$V_1$导出的子图$G[V_1]$：以$V_1$为顶点集，两个端点都在$V_1$中的边为边集的图
  - $G$的$E_1$导出的子图$G[E_1]$：以$E_1$为边集，$E_1$中边的关联顶点为点集的图
- 删除
  - 删除边$G-e$
  - 删除顶点及其关联的一切边$G-v$
- 边$e$的收缩$G \backslash e$：删除$e$并将其两个端点用一个新顶点$w$代替
- 图的基本运算
  - 并图：点集、边集分别并
  - 差图：边集做差，关联顶点作为点集
  - 交图：边集交，关联顶点作为点集
  - 环和：边集做对称差，关联顶点作为点集
  
### 2. 度数、通路与回路
- 无向图的度数$d(v)$：$v$作为边的端点的次数
- 有向图的出度$d^{+}(v)$/入度$d^{-}(v)$：作为起点/终点的次数
- 最大度$\Delta(G)$和最小度$\delta(G)$
- 悬挂顶点/悬挂边：度数为$1$的顶点/与它关联的边
- 奇度顶点/偶度顶点
- $\sum_{v\in V}d(v) = 2\vert E \vert$
  - 一条边提供两个度数
  - 有向图中，$\sum_{v\in V}d^{+}(v) = \sum_{v\in V}d^{-}(v) = \vert E \vert$
  - **奇度顶点的个数是偶数个**
- 度数列$d = (d_1, d_2, ...,d_n)$
  - 可图化：存在无向图满足该度数列
  - 可简单图化：必要条件$\Delta(G)\leq n-1$
- **非负整数列$d = (d_1, d_2, ...,d_n)$是可图化的当且仅当$\sum_{i=1}^{n}d_i$为偶数**
  - 构造：偶数个奇度顶点两两一组相连，剩余的偶数度数成环
- 设$G$为任意$n$阶无向简单图，则$\Delta(G)\leq n-1$
- 同构$\simeq $：存在点集之间的双射，具体定义略，可理解为同一个图的顶点平移至不同位置，有向图要考虑方向
  - 暂无充要条件
- $n$阶（无向）完全图$K_n$：每个顶点均与其他$n-1$个顶点相邻的$n$阶无向简单图
  - $n$阶有向完全图：两个方向的边都有
- $n$阶竞赛图：基图为无向完全图的有向图
- $k$-正则图：$\forall v \in V, d(v) = k$
- 补图：点集相同，边集为所有点相连减去原有边集
  - 自补图：与补图同构
- **通路**$\Gamma = v_{i_0}e_{j_1}v_{i_1}e_{j_2}...e_{j_l}v_{i_l}$：无向标定图中顶点与边的交替序列
  - 始点/终点
  - 长度：边的条数
  - **回路**：始点与终点相同的通路
  - **简单通路**：所有边互不相同；否则为复杂通路
    - 若始点终点相同，则为**简单回路**，否则为复杂回路
  - **初级通路（路径）**：所有顶点（除始点终点可能相同）互不相同，所有边也互不相同
    - 若始点终点相同，则为**初级回路（圈）**，奇圈/偶圈
  - 若两点（不同点）间存在通路，则存在长度$\leq n-1$的通路
    - 若长度$> n-1$则不断删去重复点间的回路
    - 同理：若两点间存在通路，则存在长度$\leq n-1$的初级通路（路径）
    - 同理：若一个点存在到自身的回路，则存在长度$\leq n-1$的回路
  
### 3. 图的连通性
- 连通：两顶点间存在通路
  - 连通关系$\sim$是$V$上的等价关系
- **连通图**：平凡图（只有一个点）或任何两个顶点都是连通的
- **连通分支**：由连通关系$\sim$在$V$上的等价类$V_i$导出的子图$G[V_i]$
  - 连通分支数$p(G)$
- 短程线：两连通顶点间长度最短的通路
- **距离$d(u,v)$**：短程线的长度
  - 非负性：$d(u,v)\geq 0$等号成立当且仅当$u=v$
  - 对称性：$d(u,v) = d(v,u)$
  - 满足三角不等式：$d(u,v)+d(v,w)\geq d(u,w)$

**无向图的连通性**

- **点割集**：设无向图$G=\langle V, E \rangle$，若存在$V' \subset V$使得$p(G-V')>p(G)$，且对于任意的$V'' \subset V'$，均有$p(G-V'')=p(G)$，则称$V'$是$G$的点割集，若$V'=\lbrace v \rbrace$，则称$v$为割点
  - 即最小的（任何它的子集都不行）、删去能使连通分支数增大的点集

- **边割集（割集）**：设无向图$G=\langle V, E \rangle$，若存在$E' \subset E$使得$p(G-E')>p(G)$，且对于任意的$E'' \subset E'$，均有$p(G-E'')=p(G)$，则称$E'$是$G$的点割集，若$E'=\lbrace e \rbrace$，则称$e$为**桥**（割边）
  - 即最小的（任何它的子集都不行）、删去能使连通分支数增大的边集
- **点连通度（连通度）$\kappa$**：**无向连通图且非完全图**时（完全图不存在点割集），

$$
  \kappa (G) = \min{\lbrace \vert V'\vert \mid V'\text{为}G\text{的点割集}\rbrace}
$$

- 即点割集的最小基数
  - **$k$-连通图**：若$\kappa(G)\geq k$，则称$G$为$k$-连通图
    - 删除任意$k-1$个顶点后一定还是连通的
- **边连通度$\lambda$**：**无向连通图**中，

$$
  \lambda (G) = \min{\lbrace \vert E'\vert \mid E'\text{为}G\text{的边割集}\rbrace}
$$

- 即边割集的最小基数
  - **$r$边-连通图**：若$\lambda(G)\geq r$，则称$G$为$r$边-连通图
    - 删除任意$r-1$条边后一定还是连通的
    - $\lambda (K_n) = n-1$，$k_n$是$r$边-连通图，$0\leq r\leq n-1$
- **非连通图的点/边连通度都为$0$**
- 对于任何**无向图**$G$，有

$$
  \kappa (G)\leq \lambda (G)\leq \delta(G)
$$

- 即**点连通度**不大于**边连通度**不大于**最小度**
  - 对于圈来说，三者相等均为$2$
  - 对于一个顶点连接两个$K_4$的情况，详见书p96，三者为小于关系

**有向图的连通性**
- 可达：存在有向通路
  - 相互可达
- 短程线和距离$d\langle v_i,v_j\rangle$定义与无向图类似
- 弱连通图（连通图）：基图为连通图的有向图
- 单向连通图：任意两个顶点至少单向可达
- 强连通图：任意两个顶点均相互可达
- **有向图$D$是强连通图当且仅当$D$中存在经过每个顶点至少一次的回路**
- 极大路径（路径端点不与路径外的点相邻）与扩大路径法证明

**二部图**
- 设无向图$G = \langle V, E \rangle$，若能将$V$划分成$V_1$和$V_2$，使得$G$中的每条边的两个端点一个属于$V_1$，另一个属于$V_2$，则称$G$为**二部图**，记作$\langle V_1, V_2, E\rangle$
  - **完全二部图$K_{r,s}$**：若$G$是简单二部图，$V_1$中每个顶点均与$V_2$中所有顶点相邻，$r=\vert V_1\vert, s = \vert V_2\vert$
  - $n \geq 2$时，零图为二部图
- **设$n \geq 2$，则$n$阶无向图$G$是二部图当且仅当$G$中无奇圈**
  - 必要性：有奇圈无法将每一对相邻点分在两个集合中
  - 充分性：
    - 不妨设为连通图，否则对每个连通分支讨论，孤立点随意放入一个集合（证明常用）
    - 任取$v_0$，构造

$$
  V_1 = \lbrace v\mid v \in V(G),d(v_0,v)\text{为偶数} \rbrace
  V_2 = \lbrace v\mid v \in V(G),d(v_0,v)\text{为奇数} \rbrace
$$

  - 下证$V_1$内任意顶点不相邻，$V_2$内任意顶点不相邻
  - 若相邻，任意两点到$v_0$的短程线加两点之间的边构成奇圈，矛盾

### 4. 图的矩阵表示
**无向图的关联矩阵$\mathbf{M} (G)$**：$m_{ij}$为顶点$v_i$与边$e_j$的关联次数
- recap：关联次数为$0,1,2$对应的情形
- 有如下性质：
  - 每列元素之和均为$2$：每条边有两个端点
  - 每行元素之和为$v_i$的度数
  - 所有元素之和为$2$倍边数
  - 两列相同当且仅当为平行边
  
**无环有向图的关联矩阵$\mathbf{M} (D)$**：
- $m_{ij} = 1,v_i\text{为}e_i\text{的始点}$
- $m_{ij} = 0,v_i\text{与}e_i\text{不关联}$
- $m_{ij} = -1,v_i\text{为}e_i\text{的终点}$
- 有如下性质：
  - 每一列有一个$+1$和一个$-1$（无环图有不同的始终点）
  - $-1$的个数$= +1$的个数$=$边数
  - 每行中$+1$的元素个数等于出度，$-1$的元素个数等于入度
  - 两列相同当且仅当为平行边
  
**有向图的邻接矩阵$\mathbf{A} (D)$**：$a_{ij}$为顶点$v_i$邻接到顶点$v_j$的边的条数
- 有如下性质：
  - 每行元素之和为该顶点的出度
  - 每列元素之和为该顶点的入度
  - 所有元素之和$=$出度和$=$入度和$=$边数
  - $\mathbf{A}^l$中元素表示顶点$v_i$邻接到顶点$v_j$的长度为$l$的通路数
    - 元素和为$D$中长度为$l$的通路数总数
  - $\mathbf{B}_l = \mathbf{A} + \mathbf{A}^2 +...+\mathbf{A}^l$中元素和为$D$中长度$\leq l$的通路数
  
**有向图的可达矩阵$\mathbf{P}(D)$**：
- $p_{ij} = 1,v_i \text{可达}v_j$
- $p_{ij} = 0,\text{否则}$
- 有如下性质：
  - 对角线上元素全为$1$
  - 非对角线上的元素，只要计算出$\mathbf{B_{n-1}}$后将非零元写成$1$即可

## 第六章 欧拉图与哈密顿图
### 1. 欧拉图
- **欧拉通路**：通过图中所有边一次且仅一次，行遍所有顶点的通路
  - 欧拉回路
- **欧拉图**：具有欧拉回路的图
  - 半欧拉图：具有欧拉通路而无欧拉回路的图
  - 规定平凡图是欧拉图
- **无向图$G$是欧拉图当且仅当$G$是连通图且没有奇度顶点**
  - 必要性：考察该欧拉图的欧拉回路（包括了所有边一次和所有点），连通性显然，每个点每出现一次获得$2$度，故度数均为偶数
  - 充分性：对边数$m$归纳，构造欧拉回路，根据偶数度数$\delta(G)\geq 2$删除一个圈后利用归纳假设
- **无向图$G$是半欧拉图当且仅当$G$是连通图且恰有两个奇度顶点**
  - 必要性：考察欧拉通路
  - 充分性：将两个奇度顶点新加边，则根据上条定理为欧拉图，将欧拉回路减去新加边得到欧拉通路
- **有向图$D$是欧拉图当且仅当$D$是强连通的且每个顶点的入度等于出度**
- **有向图$D$是半欧拉图当且仅当$D$是单向连通的且恰有两个奇度顶点，其中一个顶点的入度比出度大$1$，另一个相反，其余顶点的入度等于出度**
  - 类似无向图，考察欧拉回路和欧拉通路可证
- $G$是非平凡的欧拉图当且仅当$G$是连通的且是若干个边不重的圈的并
- Fleury算法求欧拉回路：能不走桥就不走桥

### 2. 哈密顿图
- **哈密顿通路**：经过图中所有顶点一次且仅一次的通路称作哈密顿通路
  - 哈密顿回路：过始终点两次，其余点一次
- **哈密顿图**：具有哈密顿通路的图
  - 半哈密顿图：具有哈密顿通路但不具有哈密顿回路的图
  - 规定平凡图是哈密顿图
  - 暂无判断哈密顿图的充要条件，下给出必要条件和充分条件

**必要条件**
- 设无向图$G = \langle V, E \rangle$是哈密顿图，则对于任意$V_1\subset V$且$V_1 \neq \varnothing$，均有

$$
  p(G-V_1) \leq \vert V_1 \vert
$$

- 证明：
  - 考察哈密顿回路$C$
  - 当$V_1$中元素在$C$上均不相邻时，$C-V_1$的连通分支数取最大值$\vert V_1 \vert$
  - 而$C$又是$G$生成的子图，故有$p(G - V_1) \leq p(C - V_1) \leq \vert V_1 \vert$
- 可以推出：二部图若是哈密顿图，则$\vert V_2 \vert = \vert V_1 \vert$
  - 思考：半哈密顿图的二部图有何种性质？
  - 一种确定二部图不是哈密顿/半哈密顿图的简单方法
- 设无向图$G = \langle V, E \rangle$是半哈密顿图，则对于任意$V_1\subset V$且$V_1 \neq \varnothing$，均有

$$
  p(G-V_1) \leq \vert V_1 \vert + 1
$$

- 证明：
  - 加边变为哈密顿图，删去新加边最多使连通分支数加一

**充分条件**
- 设$G$是$n$阶无向简单图，若对于$G$中任意不相邻的顶点$u,v$，均有

$$
  d(u)+d(v) \geq n-1
$$

- 则$G$中存在哈密顿通路
  - 证明：
    - 考虑最长通路，要证最长通路就是哈密顿通路
    - 由题设度数条件：最长通路中顶点数小于$n$则一定形成圈（即$n - k$时的哈密顿回路）
    - 连接圈外的点形成更长通路，矛盾
- 设$G$是$n$阶无向简单图，若对于$G$中任意不相邻的顶点$u,v$，均有

$$
  d(u)+d(v) \geq n
$$

- 则$G$中存在哈密顿回路
  - 证明：
    - 证其逆否命题
    - 设本来没有哈密顿回路，加边直至存在哈密顿回路，删去最后一条边，此时有哈密顿通路，而没有哈密顿回路
    - 哈密顿通路中，最后的端点不能与最初的端点相邻点的前一个相邻，否则有哈密顿回路
    - 即存在一对不相邻顶点度数和小于$n$
    - 故任意一对不相邻顶点的度数和$\geq n$时，存在哈密顿回路
    - 详见：[图论 - 哈尔滨工业大学（哈工大 HIT）-哔哩哔哩](https://b23.tv/U2XnWRU)
- **竞赛图中都有哈密顿通路**
  - recap竞赛图：基图为无向完全图的有向图
  - 证明：
    - 归纳，按照是否有新加点为始点的边分类
    - 暂略

## 第七章 树
*许多东西在数算里讲过*

### 1. 基本概念与性质
- 无向树（树）：**连通无回路**的无向图
- 森林：每个连通分支都是树的无向图
- 平凡树：平凡图
- 树叶：悬挂顶点
- 分支点：度数$\geq 2$的顶点
- 星形图：只有一个分支点，其度数为$n-1$
- 以下命题等价：
  - $G$是树
  - $G$中任意两个顶点存在唯一路径
  - $G$中无回路且$m=n-1$
  - $G$是连通的且$m=n-1$
  - $G$是连通的且任何边均为桥
  - $G$中无回路，但在任何两个不同顶点之间加一条新边后所得的图中有唯一一个含有新边的圈
- 树至少有$2$片树叶
  - 树叶：度为$1$
  - 用边数和度的关系可证

## 第八章 平面图（除对偶图）
### 1. 基本概念
- 平面图（可平面图）：能将无向图$G$画在平面上使得除顶点外无边相交
  - 平面嵌入：画出的无边相交的图
- 常见的平面图/非平面图
  - 平面图：$K_1, K_2, K_3, K_4, K_5 - e, K_{1,n}, K_{2,n}$
    - $K_{2,n}$把$2$分在$n$的上下两边
  - 非平面图：$K_5, K_{3,3}$
- 加平行边和环不改变平面性
  - 研究一个图是否为平面图时可以不考虑平行边和环
- **面**：平面图$G$的边将平面划分为若干个区域，每个区域都称为$G$的一个面
  - 外部面$R_0$：其中有一个面的面积无限，称为外部面（无限面）
  - 内部面$R_1, R_2, ..., R_k$：其余面积有限的面
  - **边界**：包围每个面的所有边组成的回路称为该面的边界
  - **次数$\deg{R}$**：边界的长度称为该面的次数
- 平面图所有面的次数之和等于边数的两倍（每条边被两个面作为边界）
  
**极大平面图**

- $K_1, K_2, K_3, K_4, K_5 - e$
- 极大平面图：设$G$为**简单平面图**，在$G$中任意两不相邻顶点间加一条边，所得图为非平面图
  - 无法加边的情况也算命题为真
- 极大平面图是连通的，且当阶数$\geq 3$时没有割点和桥
- **设$G$是$n\geq 3$阶简单连通的平面图，则$G$为极大平面图当且仅当$G$的每个面的次数均为$3$**
  - 必要性：在次数大于$3$的面中，不相邻点之间在面内部加线不破坏平面性，故有在面外部的连线，两组线相交矛盾
  - 充分性：由后续欧拉公式可证

**极小非平面图**

-$K_5, K_{3,3}$
- 极小非平面图：设$G$为非平面图，在$G$中任意删除一条边，所得图为平面图

### 2. 欧拉公式

$$
  n - m + r = 2
$$

- 其中$n,m,r$分别为**连通平面图**$G$的顶点数、边数和面数 
  - 对边数$m$归纳，根据是否含圈（树/有回路）分类可证
- 推广：对于有$k$个连通分支的平面图，有

$$
  n - m + r = k + 1
$$

- 外部面为同一个面
  
**由欧拉公式推出平面图的性质**
- 设$G$是连通的平面图，且每个面的次数至少为$l(\geq 3)$，则$G$的边数$m$与顶点数$n$有如下关系：
  - 判断平面图的必要条件，能推出$K_5, K_{3,3}$是非平面图
    - $K_5:l=3,K_{3,3}:l=4$（考虑最短圈的长度）
  
$$
  m \leq \frac{l}{l-2}(n-2)
$$

- 证明：

$$
\begin{align*}
  2m &= \sum_{i=1}^{r}\deg{R_i} \geq lr\\
  \text{由欧拉公式：}r &= 2 + m - n\\
  \text{代入得：}2m &\geq l(2 + m - n)\\ 
  m &\leq \frac{l}{l-2}(n-2)
\end{align*}
$$

- 推广：对于有$k$个连通分支的平面图，有

$$
  m \leq \frac{l}{l-2}(n-k-1)
$$

- 设$G$是$n(\geq 2)$阶$m$条边的极大平面图，则$m = 3n - 6$
  - 由欧拉公式和极大平面图性质可证
- 设$G$是$n(\geq 2)$阶$m$条边的简单平面图，则$m \leq 3n - 6$
- 设$G$是简单平面图，则$\delta \leq 5$
  - 由上一条性质和握手定理可证
- 如果简单连通平面图的每个面次数均为$3$，则为极大平面图
  - 由欧拉公式，极大平面图性质反证（加一条边依旧是平面图），和上一条$m \leq 3n - 6$可证

### 3. 平面图的判定
- 插入$2$度顶点$w$：将$w$插入一条边中间，使其变为两条以$w$为顶点的边
- 消去$2$度顶点$w$：逆过程
- **同胚：两个图通过反复插入、消去$2$度顶点$w$后同构**
- 图$G$是平面图当且仅当$G$中既不含与$K_5$同胚的子图，也不含与$K_{3,3}$同胚的子图
- 图$G$是平面图当且仅当$G$中既没有可以收缩到$K_5$的子图，也没有可以收缩到$K_{3,3}$的子图
  - recap收缩的定义：$2$个点$1$条边$\rightarrow 1$个点

## 第九章 支配集、覆盖集、独立集、匹配与着色（除着色）
### 1. 基本概念与定理
- **支配集**：设无向简单图$G = \langle V, E\rangle ， V^* \subseteq V$，若$\forall v_i \in V - V^{*}, \exists v_j \in V^*$，使得$(v_i,v_j) \in E$，则称$V^{*}$为$G$的一个支配集
  - 即支配集中的点与所有其外的点相邻
  - 极小支配集：任何真子集都不是支配集
  - 最小支配集：顶点数最少的支配集
  - **支配数$\gamma _0$**：最小支配集中顶点的个数
- **点独立集（独立集）**：设无向简单图$G =\langle V, E\rangle , V^{*}\subseteq V$，若$V^{*}$中任何两个顶点都不相邻，则称$V^{*}$为$G$的点独立集
  - 任何两点不相邻
  - 极大点独立集：再加入任何元素都不是独立集
  - 最大点独立集：顶点数最多的点独立集
  - **点独立数$\beta _0$**：最大独立集中顶点的个数
- **设无向简单图没有孤立点，则其极大点独立集都是极小支配集**
  - 如果不是支配集，则将没相邻的点加入独立集
  - 如果不是极小的，则有其真子集为支配集，即其中有顶点相邻
- **点覆盖集**：设无向简单图$G =\langle V, E\rangle , V^{*}\subseteq V$，若$\forall e \in E, \exists v \in V^{*}$，使得$v$与$e$相关联，则称$V^{*}$为$G$的点覆盖集，并称$v$覆盖$e$
  - 即与所有边相关联的点集
  - 极小点覆盖、最小点覆盖同上
  - **点覆盖数$\alpha _0$**：最小点覆盖中顶点的个数
- **设无向简单图没有孤立点，$V^{*} \subseteq V$，则$V^{*}$为$G$的点覆盖当且仅当$\overline{V^{*}} = V - V^{*}$为$G$的点独立集**
  - 若不是点独立集，则有相邻点连成的边没有被覆盖
  - 若补集是点独立集，则所有边被覆盖，即为点覆盖集
- 推论：设$n$阶无向简单图没有孤立点，则$V^{*}$为$G$的**极小（最小）点覆盖**当且仅当$\overline{V^{*}} = V - V^{*}$为$G$的**极大（最大）点独立集**

$$
  \alpha_0 +\beta_0 = n
$$

- **边覆盖集**：设无向简单图$G =\langle V, E\rangle$没有孤立点，$E^{*} \subseteq E$，若对$\forall v \in V, \exists e \in E^{*}$，使得$v$与$e$相关联，则称$E^{*}$为边覆盖集，并称$e$覆盖$v$
  - 即与所有点相关联的边集
  - 极小边覆盖、最小边覆盖同上
  - **边覆盖数$\alpha _1$**：最小边覆盖中的边数
  - 有孤立点时不存在边覆盖
- **边独立集（匹配）**：设无向简单图$G =\langle V, E\rangle , E^{*} \subseteq E$，若$E$中任何两条边均不相邻，则称$E^{*}$为$G$的边独立集，也称作匹配
  - 极大匹配、最大匹配同上
  - **边独立数、匹配数$\beta _1$**：最大匹配中的边数
- 设$M$为$G$的一个匹配，则
  - 称$M$中的边为**匹配边**，不在$M$中的边为**非匹配边**
  - 称与匹配边相关联的顶点为**饱和点**，其余为**非饱和点**
  - 若每个点都是饱和点，称为**完美匹配**
  - 由匹配边和非匹配边交替构成的路径称为**交错路径**，起点和终点都是非饱和点的交错路径称作**可增广的交错路径**，由匹配边和非匹配边交替构成的圈称作**交错圈**
- **（最大匹配和最小边覆盖的相互转换）**设$n$阶图$G$中无孤立点，则
  - 设$M$为$G$的一个最大匹配，对$G$中每个$M$-非饱和点均取一条与其关联的边，组成边集$N$，则$W = M \cup N$为$G$的一个最小边覆盖
  - 设$W_1$为$G$的一个最小边覆盖，若$W_1$中存在相邻的边就移去其中一条，设移去的边集为$N_1$，则$M_1 = W_1 - N_1$为$G$的最大匹配
  - $G$的边覆盖数$\alpha_1$与匹配数$\beta_1$满足：

$$
    \alpha _1 +\beta _1 = n
$$

  - 证明见书p142，用不等式（最小/最大）推出等式
- 推论：匹配数$\vert M\vert \leq$边覆盖数$\vert W \vert$；等号成立时，匹配为完美匹配，边覆盖为最小边覆盖
- **设$M$是图$G$的一个匹配，则$M$为$G$的最大匹配当且仅当$G$中不含关于$M$的可增广的交错路径**
  - 必要性：将可增广交错路径的非匹配边换成匹配边即得更大的匹配
  - 充分性：不含可增广的交错路径，取最大匹配$M_1$，考虑$M_1 \oplus M$导出的子图，推出$\vert M \vert = \vert M_1 \vert$

### 2. 二部图中的匹配
- racap二部图的定义：若能将$V$划分成$V_1$和$V_2$，使得$G$中的每条边的两个端点一个属于$V_1$，另一个属于$V_2$，则称$G$为**二部图**
- **完备匹配**：设$G = \langle V_1, V_2, E \rangle$为二部图且$\vert V_1 \vert \leq \vert V_2 \vert$，若$M$为$G$中的一个匹配且$\vert M \vert = \vert V_1 \vert$，则称$M$为$V_1$到$V_2$的完备匹配
  - 即二部图中较小的点集每个点匹配一个较大点集中的点
  - 二部图的完备匹配是最大匹配；而最大匹配不一定是完备匹配
- （二部图有完备匹配的充要条件）**二部图存在$V_1$到$V_2$的完备匹配当且仅当$V_1$中任意$k,1\leq k \leq \vert V_1 \vert,$个顶点至少与$V_2$中的$k$个顶点相邻**
  - 必要性显然
  - 充分性：反证法，考虑$V_1$中非饱和点出发的交错路径，从而得出两个点集中相邻点的个数，得出矛盾
- **$t$条件**：设二部图$G = \langle V_1, V_2, E \rangle$，如果存在正整数$t$，使得$V_1$中每个顶点至少关联$t$条边，而$V_2$中每个顶点至多关联$t$条边，那么$G$中存在$V_1$到$V_2$的完备匹配