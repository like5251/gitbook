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

三者的关系：$$f(n) = \Theta (g(n)))\Leftrightarrow  f(n) = O(g(n))$$且$$f(n) = \Omega (g(n))$$


![](http://raytaylorlin-blog.qiniudn.com/image/algorithm/%E4%B8%89%E7%A7%8D%E6%B8%90%E8%BF%91%E8%AE%B0%E5%8F%B7%E7%9A%84%E5%8C%BA%E5%88%AB.jpg)

### 等式中的渐进记号

#### 等式中渐进记号的不同含义
- $$f(n) = O (g(n))$$：表示$$f(n)$$是集合$$O (g(n))$$的成员，等价于$$f(n) \in  O (g(n))$$，读作“$$f(n) $$以 $$g(n)$$为上界”。

- $$2n^{2} + 3n + O(n^{2}) = O(n^{2})$$：表示对于等号左侧任意的匿名函数，等号右侧总存在某个匿名函数使等号成立

#### 渐进等式VS实数不等式
实数的许多性质也适用于渐进记号：
- 基本类比

$$f(n) = \Theta (g(n))   \Leftrightarrow  a = b$$   
$$f(n) = O (g(n))   \Leftrightarrow  a \leqslant  b$$
$$f(n) = \Omega (g(n)) \Leftrightarrow  a \geqslant  b$$

- 传递性

$$a = b$$ 且 $$ b = c \Rightarrow a = c$$
$$f(n) = \Theta (g(n)) $$ 且 $$  g(n) = \Theta (h(n))  \Rightarrow f(n) = \Theta (h(n))$$

$$a \leqslant b$$且$$ b \leqslant c \Rightarrow a \leqslant c$$
$$f(n) = O (g(n))) $$ 且 $$  g(n) = O (h(n))  \Rightarrow f(n) = O (h(n))$$

$$a \geqslant b$$ 且 $$ b \geqslant  c \Rightarrow a \geqslant  c$$
$$f(n) = \Omega (g(n))) $$ 且 $$  g(n) = \Omega (h(n))  \Rightarrow f(n) = \Omega (h(n))$$


- 对称性

$$a =b\Leftrightarrow b=a$$
$$f(n) = \Theta (g(n))  \Leftrightarrow g(n) = \Theta (f(n))$$

$$a \leqslant b\Leftrightarrow b\geqslant a$$
$$f(n) = O (g(n))  \Leftrightarrow g(n) = \Omega (f(n))$$


$$a \geqslant b\Leftrightarrow b\leqslant a$$
$$f(n) = \Omega(g(n))  \Leftrightarrow g(n) = O (f(n))$$











































