---
title: 【陶哲轩实分析】2.2 加法
categories:
    - Mathematic
    - Analysis
tags:
    - 加法
toc: true
date: 2018-03-20 16:35:08
---

**Abstract:** 本文继续上文自然数定义后，给出自然数的第一种简单计算，加法.
**Keywords:** 加法

<!--more-->
说明：<font face="黑体" color=#6F6FFF><B>以这种字体存在的博文，来自《陶哲轩实分析》的内容完整节选，版权归原作者和出版社所有</B></font>
## 加法


<font face="黑体" color=#6F6FFF><B>
自然数系此刻还是非常朴素的：我们只有一种运算——增长，以及一撮公理.然而现在我们可以建立起更复杂的运算，如加法.
办法如下.把5加上3，应该等同于让5增长3次——这比把5加上2多一次增长，而5加上2又是比5加上1多一次增长，5加上1又比5加上0多一次
增长，而5加上0应该恰给出5.于是我们给加法一个递归的定义如下：
</B></font>

---------------
分析多次增长运算，发现增长可以递归的进行增长，也就是当你相对5增长3次，相当于在把5增长2次的结果上再增加一次，这样不管你增加多少次，最后增长都是从老祖宗0开始增长的。所以可以进行递归定义


---------------

<font face="黑体" color=#6F6FFF><B>
定义2.2.1(自然数的加法）设 $m$ 是自然数.为使 $m$ 加上零，我们定义 $0+m:=m$ .现归纳的假定已定义好如何使 $m$ 加上 $n$ .那么把 $m$ 加于 $n++$ 则定义为 $(n++)+m :=(n+m)++$ .
</B></font>

---------------
这个定义就是我们上面思考的多次增长运算的一个准确描述，而且我们把他叫做加法运算，也就是说加法运算不是自然数的先天计算，而是一个为了简化反复的增长运算抽象出来的计算。而这个定义也很有意思，并没有定义加法是什么，而只定义其行为，也就是反复增长计算的递归行为。


---------------

<font face="黑体" color=#6F6FFF><B>
于是 $0+m$ 是 $m$ ，$1+m=(0++)+m$ 是 $m++$ ， $2+m=(1++)+m=(m++)++$ ， 依此类推.例如我们有 $2+3=(3++)++=4++=5$ .从上一节关于递归的讨论看到，我们对每个自然数都定义了 $n+m$ .这里我们把前面的一般性讨论特殊 化为 $a_n=n+m$ 及以 $f_n(a_n)=a_n++$ 的情形.注意这个定义是对称的：$3+5$ 是把5增长3次，同时 $5+3$ 是把3增长5次.当然，两者得到同一个值8.更一般地，事实上对于一切自然数 $a,b$ 成立 $a+b=b+a$ (我们将简短地予以证明)，虽然这并不是从定义立即明显看到的.
</B></font>

---------------
这段是使用上文我们讲到的关于序列的定义，给 $a_n$ 以一个单一的值，那么它赋予 $a_{n++}$ 一个单一的值 $a_{n++}=f_n(a_n)$  。这个过程可以用于定义一个增长序列，比如我们给$a_n=n+m$ 那么根据我们序列的定义 $a_{n++}=f_n(a_n)=(n++)+m$  我们来求 5+3 的值 ，就要从$a_0=0+3$  开始，那么 $a_1=(0++)+3=4,a_2=(1++)+3=5,\dots,a_{5}=(4++)+3=8$ 同理我们可以证明 3+5 ，是5增长了3次也是8 ，即5+3=3+5 但是这不足以说明 $a+b=b+a$ 因为特解和通解的差别


---------------

<font face="黑体" color=#6F6FFF><B>
注意，我们可以容易地用公理2.1、公理2.2和归纳法（公理2.5)证明两个自然数的和仍然是自然数.（为什么?）
</B></font>

---------------
证明：
1. 假设 $a,b$ 为自然数，求证 $a+b$ 是自然数
2. 归纳法证明，根据公理2.1 0是自然数，当 $a=0$ 时 $0+b=b$ 的结果是自然数，成立
3. 归纳假设 $a+b$ 是自然数
4. 那么根据加法定义 $(a++)+b=(a+b)++$  因为 $(a+b)$ 是自然数， 那么根据定理2.2 他们的后继也是自然数。
5. 证毕


---------------

<font face="黑体" color=#6F6FFF><B>
眼下关于加法我们只知道两件事：$0+m=m$ 以及 $(n++)+m=(n+m)++$ . 值得注意的是，这已足够用来演绎出我们关于加法所知道的其他一切事情.
我们从一些基本的引理开始
</B></font>

---------------

加法的定义就是两条基本情况，一个初始条件，和一个递归操作，就足以构造出加法的全部性质，真的很令人惊艳。

---------------

<font face="黑体" color=#6F6FFF><B>
引理2.2.2 对于任何自然数 $n$ ，$n+0=n$ .
注意，不能从 $0+m=m$ 直接断言此事，因为我们尚不知道 $a+b=b+a$ .
</B></font>

---------------
加法具有交换性这个我们都知道，但是未经证明，我们不能使用，所以上面个引理只能从我们已经得到的定理中证明。
引理也是一种定理，只是他是我们将要证明的定理要用到的一个结论，所以我们必须先证明其可靠性，一旦证明就可以当做结论去使用。

---------------

<font face="黑体" color=#6F6FFF><B>
证明用归纳法.基础情形 $0+0=0$ 从我们所知的对于每个自然数 $m$ 都成立 $0+m=m$ 以及0是自然数这两个事实得出.现归纳地假定 $n+0=n$ .我们要证的是 $(n++)+0=n++$ .但由加法的定义，$(n++)+0$ 等于 $(n+0)++$ ，它等于 $n++$ (由于 $n+0=n$ ).这就完成了归纳.
</B></font>

---------------
我们只知道 $0+n=n$ 不知道 $n+0$ 是几。所以我们归纳n，就得到了结论，证明过程详细严谨，就不用说什么了。


---------------

<font face="黑体" color=#6F6FFF><B>
引理2.2.3 对于任何自然数 $n$ 和 $m$ ，$n+(m++)=(n+m)++$.
再次说明，我们还不能从 $(n++)+m=(n+m)++$ 导出此事，因为我们尚不知道 $a+b=b+a$ .
证明对 $n$ 进行归纳（保持 $m$ 固定）.首先考虑基础情形 $n = 0$ .在这种情形，必须证明 $0+(m++)=(0+m)++$ 但根据加法的定义， $0+(m++)=m++$ 且 $0+m=m$ ，所以两边都等于 $m++$ ，从而彼此相等.现在我们归纳地假定 $n+(m++)=(n+m)++$ ，要证明的是
$(n++)+(m++)=((n++)+m)++$
根据加法的定义，左边是 $(n+(m++))++$ ，根据归纳假设它等于 $((n+m)++)++$ .类似地，根据加法的定义，有 $(n++)+m=(n+m)++$ .于是右边也等于 $((n+m)++)++$ .于是两边彼此相等，从而我们结束了归纳.
</B></font>

---------------
这里证明定义中被固定那个数作为增运算的对象的情况，这里我们依然没有办法使用交换律，因为我们将用这个引理来证明交换律，如果用交换律证明这个引理，再用这个引理证明交换律，那不就变成民科的套路了么。
1. 证明0的情况，显然成立
2. 归纳假设n时成立
3. 证明 n++ 时成立，利用2中假设成立的部分可以得出 n++ 时成立！
4. 证毕

归纳法中最重要的一个性质就是归纳假设部分可以当做条件使用，证明递归部分的结论！这是非常有用处的一点。

---------------

<font face="黑体" color=#6F6FFF><B>
作为引理2.2.2和引理2.2.3的一个特别的推论，我们看到 $n++=n+1$ .(为什么?）
</B></font>

---------------
至此，我们还没证明也不知道增加运算和加法运算的等价关系，也就是说我们知道加法运算是增加运算的推广，但是我们还没有找到增加运算对应到加法运算是什么。
证明：

1. 根据引理2.2.2 和 引理2.2.3 $n+(0++)=(n+0)++=n++$
2. 得出 $n+1=n++$
3. 根据等号的性质 $n++=n+1$
4. 证毕

---------------

<font face="黑体" color=#6F6FFF><B>
如早先承诺的，现在可以证明 $a+b=b+a$ 了.
命题2.2.4(加法是交换的）对于任何自然数 $n$ 和 $m$ ，$n+m=m+n$ .
证明对 $n$ 进行归纳（保持 $m$ 固定).首先考虑基础情形，即证明 $0+m = m+0$ . 根据加法的定义，$0+m=m$ ，同时根据引理2.2.2，$m+0=m$ .于是基础情形做完了.现归纳地假定 $n+m=m+n$ ，我们要证 $(n++)+m=m+(n++)$  来完成归纳.根据加法定义，（n++)+m = (n+m)++ .根据引理2.2.3，$m+(n++)=(m+n)++$ ，但根据归纳假定，这等于 $(n+m)++$ .于是 $(n++)+m=m+(w++)$ ,我们完成了归纳.
</B></font>

---------------
此证明过程非常经典，使用归纳法，先用定义和引理证明0情况，然后给出归纳假设，然后使用引理和定理证明了递归情况，有的时候证明一个命题用到的引理并不是预先想到的，而是在已经构建出证明过程中发现需要使用这个引理，是个反向得出的过程，并不是看到题设就马上想到用什么引理，可能大神能做到这种预见性。


---------------

<font face="黑体" color=#6F6FFF><B>
命题2.2.5(加法是结合的）对于任何自然数 $a,b,c$ ， $(a+b)+c=a+(b+c)$ . 证明见习题2.2.1.
</B></font>

---------------
这里第一次用到括号，括号就是有限计算的符号，这个算是一个公理性质的定义，注意这是个定义！
思路是固定其中两个变量然后对另一个变量进行归纳
证明：
1. 固定其中 $a,b$ 为任意固定的自然数,当 $c=0$ 时，根据引理2.2.2 $(a+b)+c=(a+b)+0=a+b$ 而 $a+(b+c)=a+(b+0)=a+b$  所以 当 $c=0$ 时成立。
2. 归纳假设 $(a+b)+c=a+(b+c)$
3. $(a+b)+（c++）=a+(b+(c++))$ 根据引理2.2.3 那么等号左边的算式结果是 $((a+b)+c)++$ 那么同样根据2.2.3 右边等于 $a+((b+c)++) = (a+(b+c))++$
4. 根据2中的假设，和公理2.4 得到  $((a+b)+c)++=(a+(b+c))++$ 成立
5. 证毕

思考，我们只固定了a和b而归纳c，那我们需不需要固定a和c讨论一下b以及固定下b和c讨论一下a呢？个人感觉不太必要，等号前后共三个变量，那么可以改变对错的就一个变量，因为我们不管另外两个什么情况，都能通过第三个变量调节使得等号成立，所以当固定其中两个为任意自然数归纳另一个变量的时候，就能确保等式永远成立。


---------------

<font face="黑体" color=#6F6FFF><B>
根据这条结合律我们可以把和写成 $a+b+c$ 这样的形式而无需顾虑这些数是依怎样的次序加起来的.
</B></font>

---------------

结合律的关键解决问题是计算次序，也就是我们证明了加法计算是与次序无关的，任意多的加法计算也总能递归的分割成三个部分的加法，所以上面的证明不止证明了三个自然数的加法，而是证明了任何情况下的自然数加法都满足结合律，也就是计算次序。


---------------

<font face="黑体" color=#6F6FFF><B>
命题2.2.6(消去律）设 $a,b,c$ 是自然数，满足 $a+b=a+c$ ，那么我们有 $b=c$ .
注意，我们尚不可使用减法或负数来证明这个命题，因为我们还不曾建立这些概念.事实上，这个消去律是此书后面定义减法（以及整数）的决定性依据，因为它使我们即使在减法被正式定义之前，就能进行一种“虚拟减法”
</B></font>

---------------

消去率就是消去率，你可以把它当做减法，但是他绝对不是减法，或者说他是减法的萎缩版本，因为其只用于自然数，而减法适用于所有数系。

---------------

<font face="黑体" color=#6F6FFF><B>
证明通过对a进行归纳来证明此命题.先考虑基础情形 $a = 0$ .那么，$a+b=a+c$ .根据加法的定义，此式蕴含 $b = c$ ，此为所欲证者. 现归纳地假定消去律对于 $a$ 成立（从而 $a +b=a+c$ 蕴含 $(b=c)$ ; 现在要证消去律对于 $a++$ 也成立. 换句话说，我们假定 $(a ++)+b)=(a++)+c$ 而要证明 $b=c$ . 根据加法的定义， $(a+++b=(a+b)++$ 且 $(a++)+c=(a+c)++$ ，于是有 $(a+b)++=(a+c)++$ . 根据公理2.4，有 $a+b=a+c$ .由于对于 $a$ 已有消去律，所以有 $b = c$ ，它就是所需要的.这就完成了归纳法.
</B></font>

---------------
a蕴含b 的意思就是 "如果a那么b" ,上面的证明过程非常详细，但是我们必须要思考的一点是归纳证明中我们每次要固定哪些量，归纳哪个变量，很明显，我们一般归纳研究的主要对象，消去的证明中，我们要证明的就是a能不能被消去，所以a是主要研究对象。
公理2.4反复被应用，结合律的证明用到了，消去律也用到了，提醒大家的一点是看到这种前面已经证明的公理，一定要回去看一下公理内容，虽然数学不需要背什么，但是把每个公理都对上号也是非常有帮助的，尤其是后面我们要通过练习完成的证明！

---------------

<font face="黑体" color=#6F6FFF><B>
我们现在来讨论加法如何与正性交互作用.
定义2.2.7(正自然数）一个自然数叫作是正的，当且仅当它不等于0.
</B></font>

---------------
讨论关于“正”的概念，规定不为0的自然数都是正的

---------------

<font face="黑体" color=#6F6FFF><B>
命题2.2.8 若 $a$ 是正的而 $b$ 是自然数，则 $a+b$ 是正的（于是根据命题2.2.4 $b+a$ 也是正的).
证明对 $b$ 施用归纳法.若 $b = 0$ ，则 $a+b=a+0=a$ ，它是正的，从而证实了基础情形. 现归纳地假定 $a+b$ 是正的，那么 $a+(b++)=(a+b)++$ ，根据公理2.3它不能是零，从而是正的.这就完成了归纳法.
</B></font>

---------------
这里的证明也非常清晰，就是对b进行归纳，为什么归纳b？因为b的范围比a大一些，当然这个证明也可以归纳a，结果是一样的。公理2.3的内容是0不是任何自然数的后继，所以，只要一个自然数 $a++$ 是另一个自然数 $a$ 的后继，那么 $a++$ 必然为正

---------------

<font face="黑体" color=#6F6FFF><B>
推论2.2.9 如果 $a$ 和 $b$ 是自然数，满足 $a+b=0$ ，那么 $a=0$ 且 $b=0$ .
证明假设不然，则 $a\neq 0$ 或 $b\neq 0$ .如果 $a\neq 0$，那么 $a$ 是正的，从而根据命题2.2.8， $a+b=0$ 是正的，这是一个矛盾. 类似地，如果 $b\neq0$ ，那么 $b$ 是正的，从而根据命题2.2.8，$a+b=0$ 也是正的，还是矛盾.于是 $a$ 和 $b$ 必定都是零.
</B></font>

---------------
这里我们第一次用到了反证法，就是假设结论的对立事件成立，然后证明当结论的对立事件成立的时候，和条件矛盾，从而证明命题成立，这里有逻辑上的一些概念，比如 $a且b$ 的对立事件是 $非a或非b$ ，以及“或，且，非”这些关键词的含义，这些内容应该去离散数学，或者逻辑方面的介绍，本书后面附录有相关说明，我们就不展开讨论了，因为内容太多。
证明中用到了正性的定义，我们目前的套路是，已经证明的定理，已经提出的公理，给出的定义只要已经被证明，后面就可以直接使用

---------------

<font face="黑体" color=#6F6FFF><B>
引理2.2.10 设 $a$ 是正数.那么恰存在一个自然数 $b$ ,使得 $b++=a$ .
证明见习题2.2.2.
</B></font>

---------------
中文翻译版这个地方有个错误，就是把第一个a写成了b。
思路，这里我们归纳 $a$ ，注意这个时候我们要从1开始归纳
1. 当 $a=1$ 根据公理2.1和2.2 我们可以找出 自然数 $b=0$ 满足结论 使得 $b++=a$ 成立
2. 归纳假设：存在自然数b使得。对于任意正数 a 有 $b++=a$
3. 当正数为 $a++$ 的时候，根据2中的假设有 $(b++)++=a++$  根据公理2.2 一个自然数的后继仍然是自然数，所以存在自然数 $(b++)$ 满足结论
4. 证毕


---------------

<font face="黑体" color=#6F6FFF><B>
一旦有了加法的概念，我们就可以开始定义序的概念.
定义2.2.11(自然数的排序）设 $n$ 和 $m$ 是自然数.我们说 $n$ 大于等于 $m$ ，记作$n\geq m$ 或 $m\leq n$ ，当且仅当对于某自然数 $a$，成立 $n=m+a$ .我们说 $n$ 严格大于 $m$ ，记作 $n > m$ 或 $m < n$ ，当且仅当 $n\leq m$ 并且 $n\neq m$ .
</B></font>

---------------
前一篇递归过程我们得到了序列这种对象，如果把序列中的迭代关系规定为加法运算，我们就能得到一个自然数的序列，这个序列的先后关系，或者先后位置决定了大小，我们规定后出来的大，先出来的小，也就是说自然数中0是最小的，一个自然数的后继（加1）大于他自己，这样就递归的通过改变加法的参数定义出了所有自然数的大小，关系
可能上面的定义比我的解释更清晰，因为我想套用一下序列这个概念，所以互相参考，明白就好

---------------

<font face="黑体" color=#6F6FFF><B>
于是，譬如 $8>5$ ，因为 $8=5+3$ 而 $8 \neq 5$ .还有，注意到对于任何 $n$ 都成立 $n++>n$ 于是不存在最大的自然数 $n$ ，因为下一个数 $n++$ 总是更大的.
</B></font>

---------------
举几个例子，具体数字，和用增长计算得到比自己本身大的后继，这的注意的是，我们这里并没有定义8比5大了3，虽然实际情况是这样的，但是到此我们还没定义大了多少，我们只定义了大小。

---------------

<font face="黑体" color=#6F6FFF><B>
命题2.2.12(自然数的序的基本性质）设 $a,b,c$ 是自然数.那么
(a) (序是自反的）$a\geq a$
(b) (序是传递的）若 $a\geq b$ 且 $b\geq c$，则 $a \geq c$ .
(c) (序是反对称的）若 $a\geq b$ 且 $b\geq a$ ，则 $a = b$ .
(d) (加法保序）$a\geq b$ 当且仅当 $a+c\geq b+c$.
(e) $a < b$ 当且仅当 $a++\leq b$
(f) $a < b$ 当且仅当对于某正数 $d$ ，$b=a+d$ .
证明见习题2.2.3.
</B></font>

---------------
证明：


(a)归纳a
1. $a=0$ 时，定义2.2.11 ，$0=0+0 \Rightarrow 0\geq 0$
2. 归纳假设 $a\geq a$ 成立
3. 因为 $(a++)+0=(a++)$ 所以根据定义2.2.11 $a++\geq a++$ 也成立
4. 证毕


(b)
1. 替换公理好像我们没有介绍，但是可以查一下，是逻辑上的最基本的公理，比如 $a+b=c$ 而且 $b=x+y$ 那么 $a+x+y=c$ 成立，这个可以当做公理使用不需要证明！
根据定义，$a\geq b$ 且 $b\geq c$ 那么必然存在自然数 $d_1$ 和 $d_2$ 有 $a=b+d_1$ 以及 $b=c+d_2$ 根据替换公理，$a=c+d_2+d_1$ 我们上面已经证明了自然数相加还是自然数，所以可以根据定义2.2.11 可以得到结论 $a\geq c$ 证毕


(c)反证法
1. 条件 $a\geq b$ 成立
2. 那么根据定义2.2.11 $a=b+c$
3. 又因为 $a\neq b$
4. 所以根据引理2.2.2 $c\neq 0$
5. 假设条件 $b\geq a$ 成立 且  $a\neq b$
6.  $b=a+d$  且 $d\neq 0$
7. 那么把6带入到2，就得到了 $a=a+c+d$ 同时 $a\neq 0$ 且 $b\neq 0$ 显然这是与加法的定义是矛盾的
8. 证毕


(d)使用消去率可以证明
1. 根据定义 $a\geq b$ 得到存在自然 $d$ 使得 $a=b+d$（此句证明过程可逆）
2. 根据消去律 $a+c=(b+d)+c$ (定理)
3. 那么 $a+c=(b+c)+d$ （可逆）
4. 根据序的定义，得到结论 $a+c\geq b+c$ （此句证明过程可逆）
5. 证毕（当且仅当的证明方法要从前后两个方向证明，上述证明过程全部可逆，在此不再赘述）

(e)
- 证明if过程
    1. $a++\leq b$ 根据2.2.11的定义 存在自然数c 满足 $(a++)+c=b\Rightarrow a+(c++)=b\Rightarrow a\leq b$
    2. 根据公理2.3,自然数c的后继不可能是0，所以 $c++\neq 0$
    3. 根据加法定义，所以 $a\neq b$ 又因为  $a\leq b$
    4. 得出结论 $a<b$
- 证明 only if 过程
    1. $a<b\Rightarrow a\leq b \text{ and } a\neq b$
    2. 根据定义2.2.11 那么存在自然数c 使得 $b=a+c$
    3. 因为 $a\neq b$ 那么 $c\neq 0$
    4. 根据引理2.2.10 必然有自然数 d 满足 $d++=c$
    5. 所以 $ b=a+(d++)$
    6. 根据加法结合性 $b=(a++)+d$
    7. 得出结论 $a++\leq b$
    8. 证毕

(f)根据e中的结论可以快速推出f
1. $a < b \Leftrightarrow a++\leq b$
2. 那么存在自然数c 满足 $(a++)+c=b$
3. 根据加法结合性， $a+(c++)=b$
4. 结合引理2.2.19 令 $d=c++$
5. 得出结论
6. 整个证明过程可逆，所以不需要再给出if的证明过程了
7. 证毕

---------------

<font face="黑体" color=#6F6FFF><B>
命题2.2.13(自然数的序的三歧性）设 $a$ 和 $b$ 是自然数，那么下述三命题中恰有一个是真的:
$$
a < b , a=b , a > b
$$
证明这里只给出一个证明的框架，其中的缺口将在习题2.2.4中加以弥补.
首先证明三命题 $a < b, a = b,a > b$ 中不会有多于一个的命题同时成立.若 $a < b$ 则根据定义 $a\neq b$ ，而若 $a > b$ 则根据定义 $a\neq b$ .若 $a>b$ 且 $a < b$ 则根据命 题2.2.12 必有 $a=b$ ，这是矛盾的.于是不会有多于一个的命题成立.
现在我们证明至少有一个命题成立.保持 $b$ 固定而对 $a$ 进行归纳.若 $a=0$ ，则 $0\leq b$ 对于一切 $b$ 成立（为什么?)，于是我们有 $0=b$ 或 $0 < b$ ，这证明了基础情形. 现设我们已对于 $a$ 证明了命题，而要证命题对 $a++$ 成立.从对于 $a$ 的三歧性，有三种情形：$a < b$ ，$a=b$ ，以及 $a > b$ .若 $a > b$ ，则 $a++ > b$ (为什么?).若 $a=b$ ， 则 $a++ > b$ (为什么?).现设 $a < b$ .那么根据命题2.2.12，有 $a++\leq b$ .于是或者 $a++= b$ 或者 $a++ < b$ ，而在两种情形中的每种情形下我们都完成了论证.这就完成了归纳法.
</B></font>

<font face="黑体" color=#FF0000><B>
“若 $a>b$ 且 $a<b$ 则根据命 题2.2.12 必有 $a=b$ ”这句话有问题
</B></font>

---------------
1. 为什么（若 $a=0$ ，则 $0\leq b$ 对于一切 $b$ 成立）：
    - 因为$b$ 是自然数，所以根据2.2.11的定义，$b=0+b$ 所以 $0\leq b$
2. 为什么（若 $a>b$ ，则 $a++>b$ ）：
    - 存在自然数c 满足 $a>b \Leftrightarrow a=b+c$
    - 根据引理2.2.3 $a++=(b+c)++=b+(c++)$
    - $c++\neq 0$ 根据公理2.3
    - 所以 $a++\geq b \text{ and }a++\neq b$
    - 证毕
3. 为什么（若 $a=b$ ，则 $a++>b$）
    - $a=b\Leftrightarrow a++=b++$ 公理2.4
    - 根据 $b++=b+1$ 所以 $a++=b+1$
    - 根据序的定义2.2.11 $a++\geq b$ 又因为 $a++=b++\neq b$
    - 得出结论$a++>b$
    - 证毕





---------------

<font face="黑体" color=#6F6FFF><B>
序的性质使我们可以得到归纳法原理的一个更强的形式：
命题2.2.14(强归纳法原理）设$m_0$ 是一个自然数，而 $P(m)$ 是一个依赖于任意自然数 $m$ 的性质.设对于每个 $m\geq m_0$ 都有下迷蕴含关系：如果 $P(m')$ 对于一切满足$m_0\leq m'< m$ 的自然数 $m'$ 都成立，那么 $p(m)$ 也成立（特别地，这意味着 $P(m_0)$ 成立，因为在 $m=m_0$ 的情况下，假定的条件 $P(m')$ 是空的)，那么，我们可 以断定 $P(m)$ 对于一切自然数 $m > m_0$ 都成立.
注2.2.15 在实用中我们常使用这个原理于 $m_0=0$ 或 $m_0=1$
证明见习题2.2.5.
</B></font>

---------------
证明：
1. 设性质 $Q(n)$ 为性质 “$P(m)$ 对于一切 $m_0\leq m < n$ 成立”
2. $n=0$ 时 $Q(n=0)$ 成立
3. 归纳假设$Q(n)$ : $P(m)$ 对于一切 $m_0\leq m < n$ 成立
4. $Q(n++)$ : $P(m)$ 对于 $m_0\leq m < n++$ 中 $m<n$ 中都成立，2中已经给出了假设，那么我们只需要证明 $P(n)$ 成立就可以了
5. 根据描述 “如果 $P(m')$ 对于一切满足$m_0\leq m'<m$ 的自然数 $m'$ 都成立，那么 $p(m)$ 也成立” 可以根据2得到 $P(n)$ 成立，那么我们就证明了4中的结论
6. 证毕。

评论：这个思路非常清楚，主要是找到需要归纳的那条性质，Tao 提示的非常到位，这个过程应该也比较清晰。

---------------
## 习题


<font face="黑体" color=#6F6FFF><B>
习题 2.2
2.2.1 证明命题2.2.5.(提示：固定其中两个变元而对第三个变元进行归纳)
2.2.2 证明引理2.2.10. (提示：使用归纳法.）
2.2.3 证明命题2.2.12.(提示：你要用到前面的很多命题、推论和引理)
2.2.4 验证在命题2.2.13的证明中标出 “(为什么?)” 的三个命题.
2.2.5 证明命题2.2.14，(提示：定义 $Q(n)$ 为性质“$P(m)$ 对于一切 $m_0\leq m < n$ 成立”，注 意当 $n < m_0$ 时是莫须有地成立的
2.2.6 设n是自然数且设 $P(m)$ 是一个依赖于自然数的性质，它满足条件：只要 $P(m++)$ 成立则 $P(m)$ 也成立.假设 $P(n)$ 成立，证明对于一切自然数 $m < n$ ，$P(m)$ 成立.此即所谓向后归纳原理.（提示：对变元n用归纳法.）
</B></font>

---------------
所有问题的答案都在上面能找到。

这里只证明练习 2.2.6
思路，这道题和上面那道题类似，都是找到归纳的性质就能解决问题。
证明:
1. 当 $n=1$ 时 $m < n\Leftrightarrow m=0$ 又因为 $P(n=1)$ 成了 那么 $P(0)$ 成立。
2. 归纳假设 $P(n)$ 成立 ，那么所有 $P(m) \text{ for } m<n$ 成立
3. 当 $P(n++)$ 成立时， 根据条件 $P(n)$ 也成立，再根据2中的结论 ，$P(m) \text{ for } m\leq n++$
4. 证毕

说明为什么n从1开始而不是从0开始，因为自然数中0不是任何的后继，所以，我们没办法直接让 $P(0)$ 成立，只能通过让 $P(1)$ 成立来诱导出1的前驱0成立，归纳假设和递归部分只差一个项就是 $p(n)$ 项，这就刚好使用到了2中的假设，故得以证明。

---------------
## 总结
真长！不想说话，原文可能有些地方有错误，读不通顺可以看看书，书上也有不少错的地方！那就去查原文吧。