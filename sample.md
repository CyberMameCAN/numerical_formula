# Markdown記法で、TeX/LaTeX構文での数式入力サンプル

$$
E = mc^2
$$

## 導関数の定義

$$
f'(x) = \lim_{h\to0}\frac{f(x+h)-f(x)}{h}
$$
## 二次方程式の解

When $a \ne 0$, there are two solutions
to $(ax^2 + bx + c = 0)$ and they are 

$$
x = {-b \pm \sqrt{b^2-4ac} \over 2a}
$$

## 積の部分

$$
(f(x)g(x))' = f'(x)g(x) + f(x)g'(x)
$$

## 商の微分

$$
y = \frac{f(x)}{g(x)} => \frac{dy}{dx}=\frac{f'(x)g(x)-f(x)g'(x)}{(g(x))^2}
$$

## 指数関数の微分

$$
y=a^x => \frac{dy}{dx}=a^{x}log_{e}a\qquad(a>0, a\ne1)
$$

## 平均二乗誤差(損失関数)

$$
E(w_1, w_2, b) = \frac{1}{4}\sum_{n=0}^3 (t_n - y_n)^2
$$

## 統計関係

xは$\mathbb{R}$に属する

$$
x \in \mathbb{R}
$$

### 分散

$$
S_x^2 = \frac{1}{n}\sum_{i=1}^nx_i^2 - \bar{x}^2
$$

### 変動係数

$$
\frac{S_x}{\bar{x}}
$$

### 共分散

$$
S_{xy} \frac{1}{n}\sum_{i=1}^n(x_i-\bar{x})(y_i-\bar{y})
$$
次の公式もある
$$
S_{xy} = \frac{1}{n}\sum_{i=1}^nx_iy_i-\bar{x}\bar{y}
$$

### 相関係数

$-1 \le r_{xy} \le 1$ の範囲

$$
r_{xy} = \frac{S_{xy}}{S_xS_y}
$$

### 集合

$$
P({A}\cup{B}) = P(A) + P(B)
$$
$$
P({A}\cap{B}) = P(A)P(B)
$$

#### 条件付き確率
$$
P(A|B) = \frac{P({A}\cap{B})}{P(B)}
$$
#### ベイズの定理
$$
P(A|B) = \frac{P(A)P(B|A)}{P(A)}
$$

### 確率変数Xの期待値と分散の関係
$$
V(X) = E(X^2) - \{E(X)\}^2
$$

### 確率変数X, Yの共分散
$$
Cov(X, Y) = E[(X-E(X))(Y-E(Y))]
$$
次の公式もある
$$
Cov(X, Y) = E(XY)-E(X)E(Y)
$$

### 確率変数X, Yの相関係数
$$
\rho(S,T) = \frac{Cov(X,Y)}{\sqrt{V(X)\sqrt{V(Y)}}}
$$

### 連続型確率密度関数

$$
P(a\le{X}\le{b}) = \int_a^b f(x)dx
$$
#### Xの期待値
$$
E(x) = \int_{-\infty}^\infty xf(x)dx
$$

#### Xの分散
$$
V(X) = \int_{-\infty}^\infty (x-E(x))^2f(x)dx
$$

### 二項分布

$$
P(X=x) = \frac{n!}{x!(n-x)!}p^x(1-p)^{n-x}
$$

### ポアソン分布
離散確率分布  
ある出来事が一定時間内に一定の回数($\lambda$)回起こる時の確率分布

$$
P(X=x) = \frac{e^{-\lambda}・\lambda^x}{x!}\qquad(x=0,1,2,・・・)
$$

#### 参考
$$
e = \lim_{x\to0}(1+x)^{\frac{1}{x}}
$$

## 区間推定

### 母平均の推定（母分散が既知, 95%信頼区間）

$$
\bar{X} - 1.96\times\frac{\sigma}{\sqrt{n}}\le\mu\le\bar{X} + 1.96\times\frac{\sigma}{\sqrt{n}}
$$

## 勾配降下法

$$
w_1 \leftarrow w_1 - \eta\frac{\partial E(w_1, w_2, b)}{\partial w_1}\\
w_2 \leftarrow w_2 - \eta\frac{\partial E(w_1, w_2, b)}{\partial w_2}\\
b \leftarrow b - \eta\frac{\partial E(w_1, w_2, b)}{\partial b}
$$

## 動的計画法(TD法?)

R(s): 状態ｓでの報酬

$$
V(s) = R(s) + \gamma \max_a \sum_{s^{\prime}} T(s^{\prime} | s, a)V(s^{\prime})
$$

- 価値反復法  
最初、V(s)を適当に決めて、V0=0とする。