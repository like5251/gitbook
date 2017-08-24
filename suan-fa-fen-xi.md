# 算法分析
算法效率的度量是通过时间复杂度和空间复杂度来描述的。


## 渐进表示法

### 渐进记号
渐进记号要求每个成员都渐进非负，以下c c1 c2 均为正数常量。
- $$\Theta (g(n))$$是以$$g(n)$$为渐进确界的所有函数集合

$$
\Theta (g(n)) = \left \{ f(n) | c_{1}\leqslant  \lim_{n \to \infty  }  \frac{f(n)}{g(n)} \leqslant c_{2} \right \}
$$

- $$O (g(n))$$是以$$g(n)$$为渐进上界的所有函数集合

$$
O (g(n)) = \left \{ f(n) | \lim_{n \to \infty  } \frac{f(n)}{g(n)} \leqslant c  \right \}
$$

- $$\Omega (g(n))$$是以$$g(n)$$为渐进下界的所有函数集合

$$
\Omega (g(n)) = \left \{ f(n) | c \leqslant \lim_{n \to \infty  } \frac{f(n)}{g(n)} \right \}
$$





















