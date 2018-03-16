# Mokey

Q:
 猴子第一天摘下若干个桃子，当即吃了一半，还不过瘾就多吃了一个。第二天早上又将剩下的桃子吃了一半，还是不过瘾又多吃了一个。以后每天都吃前一天剩下的一半再加一个。到第10天刚好剩一个。问猴子第一天摘了多少个桃子？
A:
分析: 这是一套非常经典的算法题，这个题目体现了算法思想中的递推思想，递归有两种形式，顺推和逆推，针对递推，只要我们找到递推公式，问题就迎刃而解了。
    令S10=1，容易看出 S9=2(S10+1)， 简化一下
       S9=2S10+2
       S8=2S9+2
       .....
       Sn=2Sn+1+2

 下一步我们就要计算一下这个递归的时间复杂度是多少，关于求“递归”的时间复杂度主要有三种：
1.  代换法。
2.  递归树法。
3.  主定理。

 这一篇我就说下代换法，作法如下
①：猜一下递归式复杂度的上界或者下界。
②：用数学归纳法证明你的复杂度是正确的。

  为了具有通用性，我们将“猴子吃桃”的问题反过来写，也就是已知S1，求S10，当然原理是一样的，通用公式就有如下形式：
             Tn=2Tn-1+2            ①
  假使
              Tn=O(n)              ②
  则必定存在一个 c>0的自然数使
              Tn<=cO(n)=cn         ③
  ③代入①知
              Tn<=2c(n-1)+2=2cn-2c+2
              =cn-c+1
              =cn-(c-1)
  当c>=1时，则必有 Tn<=cn
  最后得出递归式的时间复杂度为O(N)。