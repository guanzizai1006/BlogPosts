---
title: 【陶哲轩实分析】3.3 函数(I)
categories:
    - Mathematic
    - Analysis
keywords:
    - 函数
    - 满设
    - 映上
    - 单射
    - 双射
toc: true
date: 2018-04-17 16:43:56
---

**Abstract:** 本文介绍函数的定义和性质
**Keywords:** 函数，满设，映上，单射，双射

<!--more-->
说明：<font face="黑体" color=#6F6FFF><B>以这种字体存在的博文，来自《陶哲轩实分析》的内容完整节选，版权归原作者和出版社所有</B></font>
## 函数
<font face="黑体" color=#6F6FFF><B>
为了搞实分析，仅有集合的概念并不特别有用，我们还需要从一个集合到另一个集合的函数（function)的概念.非正式地说，从一个集合 $X$ 到另一个集合 $y$ 的函数$f: X \to Y$ 是一个运算，它对于 $X$ 中的每一个元素（或“输入” (input))指定 $Y$ 中单一一个元素（或“输出”(output))与之对应;上一章中当我们讨论自然数时己经非正式地使用了这个概念.正式的定义如下.
</B></font>

---------------
我们只知道自然数，和关于集合的一点点知识，我们就要研究函数了，可见函数是多么基础，但是其性质又是那么困难，难到不少人看到 $f(x)$ 这个符号就开始不舒服，但是函数确实是从静态到动态的关键一步，这是人类文明的一大步。
其实前面置换公理已经基本有了函数的样子了，但是唯一不同的是输入输出规定不太一样，我们还是先来看看函数是啥，然后再跟置换公理进行的对比，也能得出一些函数需要注意的特性。
函数像是一个流水线，从一个集合（输入）中挑一个对象，放到流水线上，得到一个对象，再放入另一个集合（输出）中，不过输出集合中的对象不一定都是从流水线上来的。

---------------

<font face="黑体" color=#6F6FFF><B>
定义3.3.1(函数）设 $X,Y$ 是集合，并设 $P(x，y)$ 是一个涉及对象: $x\in X$ 及对 象 $y\in Y$ 的性质，使得对于每个: $x\in X$ ,恰有一个 $y\in Y$ 使得 $P(x,y)$ 成立（此事有时叫作垂线判别法（vertical line test)).那么我们定义由 $P$ 在定义域 $X$ 和值域 $Y$ 上确定的函数 $f: X\to Y$ 是这样的对象，它对于给定的任意的输入 $x\in X$ 指定一个输出 $f(x)\in Y$ ，它是唯一的使 $P(x,f(x))$ 成立的对象.于是对于任何 $x\in X$ 和 $y \in Y$ ,
$$
y = f(x)\Longleftrightarrow P(x，y)\text{成立}
$$
</B></font>

---------------
函数的定义，注意，这个定义非常重要，因为我们从开始学函数的时候比较关注的是其映射规则，而对定义域和值域不太重视，起码我上初中学函数的时候是对定义域和值域没有要求的，但是这两个集合和映射规则同样重要，注意恰有一个 $y \in Y$ 满足 $P(x,y)$ 没错，这就是和替换公理最大的不同，替换公理没有这个限制，所以满足这个限制才能称为一个函数，普林斯顿微积分读本中关于垂线判别法有比较详细的微积分用途，这里给出了其根本来源，就是定义。 $P(x,y)$ 在分类公理和替换公理有明确的说明，这是个性质，可以是真，也可以是假，但是是一个明确的命题，不能模棱两可，其成立时x和y以及之间的关系，就是完整的函数关系。
进一步，我们更常见的写法是 $y=f(x)$ 其和 $P(x,y)$ 成立 等效

---------------

<font face="黑体" color=#6F6FFF><B>
根据上下文，函数也叫作映射或变换.有时也称之为态射（morphism),虽然更精确地说，态射指的是更为一般的一类对象，它们实际上可能相当于函数也可能并不相当于函数，具体要依上下文而定.
</B></font>

---------------
函数的别名

---------------

<font face="黑体" color=#6F6FFF><B>
例3.3.2 设 $X = \mathbb{N}，Y = \mathbb{N}$ ，且设 $P(x,y)$ 是性质 $y=x++$ ，那么对于每个 $x\in \mathbb{N}$ ，存在恰恰一个 $y$ ，使 $P(x，y)$ 成立，即 $y=x++$ .于是可以定义一个关联于此性质的函数 $f:\mathbb{N} \to \mathbb{N}$ ，使得对于一切 $x$ ， $f(x)=x++$ ;这就是 $N$ 上的增长函数，它取自然数为输入而转化到它的增长为输出.例如 $f(4) = 5$ ，$f(2n + 3) = 2n + 4$ ,依此类推.人们也可能希望定义一个减少函数 $g:\mathbb{N}\to\mathbb{N}$ 关联于由 $y++=x$ ;确定的性质 $P(x，y)$ ，即 $g(x)$ 应该是一个增长为 $x$ 的数.不幸的是，这定义不了一个函数， 因为当: $x=0$ 时，不存在增长等于 $x$ 的自然数 $y$ (公理2.3).另一方面，我们可以合理地定义一个减少函数 $h: \mathbb{N}\setminus \{0\} \to \mathbb{N}$ 关联于由 $y ++=x$ 确定的性质 $P(x,y)$ ，因为当 $x\in\mathbb{N} \setminus\{0\}$ 时，的确恰有一个自然数 $y$ 使得 $y++=x$ ,这要感谢引理2.2.10. 于是，例如 $h(4)=3$ 且 $h(2n + 3)=2n+ 2$ ,但 $h(0)$ 是无定义的，因为 $0$ 不在定义域 $\mathbb{N}\setminus\{0\}$ 之中.
</B></font>

---------------
上篇替换公理的例子，集合中每个对象进行自增运算
在定义一个自减运算的时候就出现了定义域的问题，如果只关心规则，那么很有可能定义出来有缺陷的函数，比如我们在自然数的公里中明确说 0没有前驱，所以0自减显然是没定义的，这里不能说错，但是在自然数系确实没定义，但是在其他数系就不一定了，所以定义在整数（假装我们已经学了）的自减函数和自然数上的自减函数是完全不同的两个函数

---------------

<font face="黑体" color=#6F6FFF><B>
例3.3.3(非正式的）这个例子用到了我们将在第5章定义的实数系 $\mathbb{R}$ .人们可以试图定义平方根函数 $\sqrt{} : \mathbb{R} — \mathbb{R}$ 关联于由 $y^2=x$ 确定的性质 $P(x,y)$ ,即我们要让 $\sqrt{x}$ 是使 $y^2=x$ 的数 $y$ .不幸的是此处有两个问题不允许这个定义确实建立一个函数.第一个问题是，存在实数 $x$ ,使得 $P(x,y)$ 永不成立，例如如果 $x = -1$ , 那么就不存在实数 $y$ 使得 $y^2 =x$ .然而这个问题可以经过把定义域从 $\mathbb{R}$ 限制到右半直线 $[0，+\infty)$ 来解决.第二个问题是，即使 $x\in[0,+\infty)$ ，也可能有多于一个的 $y$ 在值域 $\mathbb{R}$ 中，使得 $y^2 = x$ ，例如；如果 $x == 4$ 则 $y=2$ 和 $y=-2$ 两者都符合性质，即 $+2$ 和 $-2$ 两者都是 $4$ 的平方根.然而这个问题可以经过把值域 $\mathbb{R}$ 限制到 $[0，+\infty)$ 来解决.这样做了以后，就可以正确地使用关系式 $y^2 =x$ 定义一个平方根函数 $\sqrt{ } : [0, +\infty) \to [0, +\infty)$，于是 $\sqrt{x}$ 就是使得 $y^2= x$ ;的唯一的数 $y\in[0, +\infty)$ .
</B></font>

---------------
上面是输入减1类似的函数，其实这里我们可以看出来，运算和函数其实是非常相似的，就像用C++写程序重载符号一样，运算重载就是写个新的函数来替代原来的运算符号，通过自增的逆运算，我们发现0的自减在自然数内没有定义，于是我们第一个想法是规定一个0自减的结果，但是会与自然数公理冲突，如果推翻自然数公理，那就是削足适履了，所以另一个想法是扩展自然数系。同样这个例子在一次告诉我们自然数系太小，很多运算不能做。
然后对应于两个自然数相乘得到另一个自然数，我们想知道一个自然数是哪两个自然数相乘得到的自己 $P(x,y)$ 表示的是 对于任意 $x\in \mathbb{N}$ 都有 $y\in \mathbb{N}$ 使得 $x=y^2$ 成立，不过这似乎是不可行的，因为我们没办法说出 $x=2$ 时候满足 $P$ 的 $y$
假设我们学过有实数，那么，就能定义出一个满足 $x\in\[0,+\infty)$ 的函数，进一步定义 $x$ 为全体实数的开方操作，需要引入更大的数系，虚数，所以我们先就研究到实数吧，避免走的步子太大，扯到ball
这个例子的主要目的也是根据函数变换确定定义域值域的过程介绍，所以，大家千万注意定义域。

---------------

<font face="黑体" color=#6F6FFF><B>
定义一个函数的通用的方式是简单地确定其定义域、值域以及如何从每个输入 $x$ 产生一个输出 $f(x)$ ;这叫作函数的显式定义.例如，在例3.3.2中，函数 $f$ 可以明显地指出其定义域和值域等于 $\mathbb{N}$ ，且对于一切 $x \in \mathbb{N}$ 来定义 $f(x)=x++$ . 另一种定义一个函数 $f$ 的方式是，我们只确定何种性质 $P(x，y)$ 把输入 $x$ 和输出 $y$ 联系起来；这就是函数的隐式定义.例如，例3.3.3中的平方根函数 $\sqrt{x}$ 是以隐 含的方式经关系式 $\sqrt{x}^2=x$ 来定义的.注意，一个隐式定义仅当我们知道对于每个输入存在恰恰一个输出符合隐式关系时才成立.在很多情况下，我们为了简洁而不指明函数的定义域和值域，于是我们就可能把例3.3.2中的函数说成是“函数 $f(x):=x++$ ”、“函数 $z\mapsto x++$ ”、“函数 $x++$ ”或者极端简短地写成但是，太过简缩可能也是危险的;有时明确得知什么是函数的定义域和值域是重要的.
</B></font>

---------------
函数定义一般是明确的给出定义域和值域，接着数学家们又开始懒了，于是他们美其名曰隐式定义，也就是我不写，你自己看着表达式是猜，但是如果这个关系对于很多数系都适用，我们可以选择较大的，也可以根据题目本身的信息选择，这时，我们省略了定义域和值域的说明，直接写出函数关系，也就完成函数的隐式定义。

---------------

<font face="黑体" color=#6F6FFF><B>
我们注意到函数遵从代入公理：如果 $x=x'$ ,那么 $f(x)=f(x')$ (为什么?)，换句话说，相同的输入产生相同的输出.另一方面，不同的输入不必一定产生不同的输出，如下例所示：
</B></font>

---------------
接着我们看看函数满足带入公理，如果一个集合中两个对象 $x=x'$ 那么根据函数定义，我们可以得到 $y=f(x),y'=f(x')$ 如果 $y=y'$ 那么就说明函数满足代入公理，因为代入后 $f(x)=f(x')$ 。那么我们来证明函数满足代入公理
证明：
1. 假设函数不满足带入公理，也就是说 如果 $x=x'$ ,那么 $f(x)\neq f(x')$
2. 根据函数定义， $f(x)$ 是满足 $P(x,f(x))$ 的唯一输出， $f(x')$ 是满足 $P(x',f(x'))$ 的唯一输出，这时 $f(x)\neq f(x')$ 那么 $x \neq x'$ （否则 $f(x')$ 和 $f(x)$ 同时是满足 $P(x,y)$ 这与定义矛盾）
3. 与条件矛盾，因为条件中 $x=x'$ 所以1中假设不成立。


---------------

<font face="黑体" color=#6F6FFF><B>
例3.3.4 设 $X = \mathbb{N}，y = \mathbb{N}$ ,并设 $p(x,y)$ 是性质 $y=7$ .那么对于每个 $x\in\mathbb{N}$ 肯定恰有一个 $y$ 使 $P(x,y)$ 成立，此 $y$ 即数字 $7$ .于是我们可以构作关联于此性质的函数 $f:\mathbb{N} \to\mathbb{N}$ ;它简单地是一个常值函数，它对每个输入 $z\in\mathbb{N}$ 都指定输出 $f(x)= 7$ .于是，对于不同的输入肯定可能产生同一个输出.
</B></font>

---------------
上面我们证明了不同输出必然对应不同输入，但是现在来看这个例子就是相同输出也可以对应不同输入。
上面这个例子构造另一个常值函数，与初等数学学习常值函数不同，我们从集合的角度出发，从一个自然数集合映射到一个只有一个常数的集合，用集合映射来表现出多对一的关系。

---------------

<font face="黑体" color=#6F6FFF><B>
注3.3.5我们现在使用括号“（）”来表示数学中的几种不同的事情.一方面 我们用括号来标示运算的次序（例如，比较一下 $2+(3\times4)=14$ 和 $(2 + 3)\times4=20$ ， 但另一方面，我们也用括号来把函数 $f(x)$ 的变元或性质如 $P(x)$ 的变元包起来
然而，括号的这两种用法通常在上下文中是不会混淆的.例如，如果 $a$ 是一个数，则 $a(b+c)$ 表示表达式 $a\times(b+c)$ ,而如果 $f$ 是一个函数，则 $f(b+c)$ 表示当输入是 $b+ c$ 时 $f$ 的输出.有时函数的变元用下标来表示以取代括号.例如，自然数的一个序列 $a_0,a_1,a_2,\dots$ 严格地说是一个从 $\mathbb{N}$ 到 $\mathbb{N}$ 的函数，只不过表示作 $n\mapsto a_n$ 而不是 $n\mapsto a(n)$ .
</B></font>

---------------
不要被括号弄迷糊，括号有很多用法，比如计算优先级，函数的输入都要使用括号。


---------------

<font face="黑体" color=#6F6FFF><B>
注3.3.6严格地说，函数不是集合，而集合也不是函数.问一个对象 $x$ 是不是一个函数 $f$ 的元素，是毫无意义的；同时，把一个对象 $x$ 作为一个集合的输入而产生输出 $A(x)$ 也是毫无意义的.另一方面，可以从一个函数 $f:X\to Y$ 出发而构作它的图像 $\{(x,f(x)):x\in X\}$ ，它完全地描述了此函数：见§3.5.
</B></font>

---------------
函数不是集合，函数是一种映射关系，并且包含了定义域和值域的这么一个“包”

---------------

<font face="黑体" color=#6F6FFF><B>
我们现在来定义关于函数的一些基本概念（concept)和基本观念（notion).第一个概念就是相等.
</B></font>

---------------
接着我们就要围绕函数来研究一些性质和操作了，我们到目前为止学了一个简单自然数系，简单的集合，以及函数，这是三个不同的东西，但是他们相互之间关系非常密切。
自然数我们研究的第一个关系是相等
集合我们研究的第一个关系也是相等
然后我们继续研究函数的相等

---------------

<font face="黑体" color=#6F6FFF><B>
定义3.3.7(函数相等）具有相同的定义域和相同的值域的两个函数 $f:X\to Y,g:X\to Y$ 叫作是相等的，记为 $f=g$ 当且仅当对于一切 $x\in X,f(x)=g(x)$ .
(如果 $f(x)$ 和 $g(x)$ 对于 $x$ 的某些值是一样的，但对于另外的值是不一样的，那么我们不认为 $f$ 和 $g$ 是相同的)
</B></font>

---------------
函数相等的的定义，就是所有部分都相等，函数三部分，定义域，值域，映射关系，这三个都相等的函数才是相等的函数。

---------------

<font face="黑体" color=#6F6FFF><B>
例3.3.8 函数 $x\mapsto x^2+2x+1$ 与函数 $x\mapsto(x+1)^2$ 在定义域 $\mathbb{R}$ 上是相等的.函数 $x \mapsto x$ 与函数 $x\mapsto |x|$ 在正实数轴上是相等的，但在 $\mathbb{R}$ 上不相等.于是，函数相等的概念可能依赖于定义域的选择.
</B></font>

---------------
一个例子，两个关系都满足映射关系相同，但是定义域决定了函数是否相等，我估计没人会区分不出来 $f(x)=x-1$ 和 $g(y)=y+1$ 是不等的，但是可能就有人区分不出来  $f(x)=x$ 和 $g(x)=|x|$ 是不相等的因为在 $\mathbb{N}$ 上他们是相等的，但是在 $\mathbb{R}$ 上式不相等的。


---------------

<font face="黑体" color=#6F6FFF><B>
例3.3.9 函数的一个相当无聊的例子是从空集到一个任意的集合的空函数 $f:\emptyset \to X$ .由于空集不含元素，我们无须给 $f$ 指定任何输出.但不管怎样说，既然空集是一个集合，空函数就是一个函数，尽管它不是一个有什么意思的函数.注意，对于每个集合 $X$ ，仅存在唯一一个从 $\emptyset$ 到 $X$ 的函数，因为定义3.3.7断言,一切从 $\emptyset$ 到 $X$ 的函数都是相等的.（为什么?）
相等这个概念遵从常用的公理（习题3.3.1).
</B></font>

---------------
空函数，定义域是空集，然后值域是任意集合，满足这个关系的函数对应一个值域只有一个。
证明一切从 $\emptyset$ 到 $X$ 的函数都是相等的，
证明：
1. 假设存在不相等的两个关系 $f,g$ 是 $\emptyset$ 到 $X$ 的函数
2. 根据1中信息，定义域和值域 $f,g$ 是完全相等的，所以我们只研究映射关系。
3. 那么对于 $X$ 中某元素 $x\in X$ 必然有不同的两个来自空集的元素 $a_1\in\emptyset$,a_2\in\emptyset$ 使得 $f(a_1)=g(a_2)=x$ 明显，根据空集的公理，不存在这样的 $a_1,a_2$,
4. 1中假设是荒谬的，证毕

习题3.3.1的证明如下（吐槽一下，本课的习题非常多）
(a) 自反性 $f(x)=f(x)$
证明：
1. 根据函数相等的定义，我们知道 $f(x)$ 和 $f(x)$ 的定义域和值域相等
2. 对于定义域内的任意元素 $x$ 必然有 $f(x)=f(x)$
3. 所以 $f(x)=f(x)$ 成立，函数是自反的。

(b) 对称的 $f(x)=g(y)$ 那么 $g(y)=f(x)$
证明:
1. 根据函数定义，可知， $f(x),g(y)$ 定义域和值域相等，且在当 $x=y$ 的时候 $f(x)=g(y)$
2. 那么在 $y=x$ 的时候也有 $g(y)=f(x)$
3. 所以函数相等是对称的。

(c) 传递的 如果 $f(x)=g(y),g(y)=h(z)$ 那么 $f(x)=h(z)$
1. 因为 $f(x)=g(y)$ 所以他们俩的值域和定义域相等，同理可以得到  $g(y)=h(z)$ 定义域值域相等
2. 根据集合相等的传递性，那么 $f(x)，h(z)$ 值域和定义域相等。
3. 对于定义域中 $x=y$ 必然有 $f(x)=g(x)$
4. 对于定义域中 $y=z$ 必然有 $g(y)=h(z)$
5. 那么就有 $x=y=z$ 且 $f(x)=g(y)=h(z)$
6. 所以 $f(x)=h(z)$
7. 传递性证毕

---------------

<font face="黑体" color=#6F6FFF><B>
对于函数，一个基础性的可执行的运算是复合.
定义3.3.10(复合）设 $f:X\to Y$ 和 $g:Y\to Z$ 是两个函数，使得 $f$ 的值域与 $g$ 的定义域是同一个集合.那么可以定义两个函数 $g$ 与 $f$ 的复合为由公式
$$
(g\circ f)(x):=g(f(x))
$$
明确定义的函数.如果 $f$ 的值域与 $g$ 的定义域并不一致,我们认为复合 $g\circ f$ 是无定义的.
容易验证，复合遵从代入公理（习题3.3.1).
</B></font>

---------------
函数是可以复合的就像做完加法还可以再做一次一样，函数是从一个集合 $A$ 映射到另一个集合 $B$ 之后还可以在映射到 $C$ 集合，但是如果这是两个函数，那么第一个输出的集合（值域）和第二个函数的输入集合（定义域）必须相等，否则复合是无意义的。
复合的写法是画圈，但是计算顺序需要注意，先算右边的函数，然后是左边的。
习题3.3.1 中的证明在后面习题中给出。

---------------

<font face="黑体" color=#6F6FFF><B>
例3.3.11 设 $f:\mathbb{N} \to\mathbb{N}$ 是函数 $f(n) := 2n$ ,并设 $g:\mathbb{N} \to\mathbb{N}$ 是函数 $g(n) := n + 3$ .那么 $g\circ f$ 是函数
$$
f\circ g(n) = g(f(n))=g(2n)=2n+3
$$
于是，例如 $g\circ f(1)=5$ ，$g\circ f(2) = 7$ ,依此类推.与此同时，$f\circ g$ 是函数
$$
f\circ g(n)=f(g(n))=f(n+3)=2(n+3)=2n+6
$$
于是，例如 $f\circ g() = 8$ ， $f\circ g(2) = 10$,依此类推.
</B></font>

---------------
一个函数复合的例子，主要注意的还是定义域值域的问题。

---------------

<font face="黑体" color=#6F6FFF><B>
上例表明，复合不是交换的：$f\circ g$ 与 $g\circ f$ 不必是同一个函数.然而复合是结合的：
</B></font>

---------------
先不管映射关系是否是复合的，但看定义域，如果 $f\circ g$ 有意义，那么必然有 $f$ 的值域为 $g$ 的定义域，而对 $f$ 的定义域和 $g$ 的值域没有要求，如果直接复合 $g\circ f$ 很大可能是没有意义的，所以不满足交换律
结合律如下：

---------------

<font face="黑体" color=#6F6FFF><B>
引理3.3.12(复合是结合的）设 $f:W\to Y,g:Z\to W$ ，且 $h:X\to Z$ 都是函数.那么
$$
f \circ(g \circ h) =(f\circ g)\circ h
$$
证明由于是 $g\circ h$ 从 $X$ 到 $W$ 的函数，从而 $f\circ(g\circ h)$ 是从 $X$ 到 $Y$ 的函数.类似地 $f\circ g$ 是从 $Z$ 到 $Y$ 的函数，从而 $(f\circ g)\circ h$ 是从 $X$ 到 $Y$ 的函数.那么 $f \circ(g \circ h)$ 和 $(f\circ g)\circ h$ 有同样的定义域和值域.为了证明它们相等，从定义3.3.7 看到，必须验证对于一切 $x\in X$ ，
$$
f \circ(g \circ h)(x) =(f\circ g)\circ h(x)
$$
但根据定义3.3.10,
$$
\begin{aligned}
f \circ(g \circ h)(x) &=f(( g\circ h)(x))\\
&=f(g(h(x)))\\
&=(f\circ g)(h(x))\\
&=((f\circ g)\circ h)(x)
\end{aligned}
$$
这就是所要证的.
</B></font>

---------------
证明过程，首先还是明确定义域和值域，然后通过复合的定义，把复合改成普通的函数形式，然后重新组合，得出结论，结合性是满足的。

---------------

<font face="黑体" color=#6F6FFF><B>
注3.3.13 注意在表达式 $g\circ f$ 中，当 $g$ 出现在 $f$ 的左边时，函数 $g\circ f$ 首先使用最右端的函数 $f$ 而后再使用 $g$ 此事常引起混淆；发生混淆的原因是，我们总是把函数 $f$ 放在它的输入 $x$ 的左边，而不是右边.（也有另外的不同的数学记号，其中把函数放在它的输入的右边，于是代替 $f(x)$ 我们得写 $xf$ ，但此记号常被证明不是把事情搞清晰了而是搞得更糊涂了，因此尚不能得到普遍使用.）
</B></font>

---------------
注意复合操作的先右边计算。

## 总结
为了控制篇幅，下半部分见下文。