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

## 積の微分

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

## ネイピア数

$$
e=\lim_{h\to0}(1+x)^{\frac{1}{x}}
$$

## オイラーの等式

幾何学の$\pi$、代数学のi、解析学のe

$$
e^{i\pi} +1 = 0
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

### 標準化変量(標準化得点)

(得点 - 平均) / 標準偏差

$$
z_i = \frac{x_i-\bar{x}}{S_x}
$$

### 変動係数

標準偏差 / 平均値

$$
\frac{S_x}{\bar{x}}
$$

### 共分散

値のばらつきを表す指標

$$
S_{xy} = \frac{1}{n}\sum_{i=1}^n(x_i-\bar{x})(y_i-\bar{y})
$$

次の公式もある

$$
S_{xy} = \frac{1}{n}\sum_{i=1}^nx_iy_i-\bar{x}\bar{y}
$$

### 相関係数
xとyの間の共分散 / (xの標準偏差 * yの標準偏差)

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

この式より導くことが出来る。

$$
p(A,B)=p(B|A)p(A)=p((A|B)p(B)
$$

### 分散の公式 (確率変数X)

$$
V(aX + b) = a^2V(X)
$$

#### 確率変数XとYが独立のならば

$$
V(X+Y) = V(X) + V(Y)
$$

#### 分散と共分散の関係

$$
V(X+Y) = V(X) + V(Y) + 2*Cov(X, Y)
$$

### 期待値と分散の関係 (確率変数X)

$$
V(X) = E(X^2) - \{E(X)\}^2
$$

### **共分散** (確率変数X, Y)

$$
Cov(X, Y) = E[(X-E(X))(Y-E(Y))]
$$

$$
= E(XY)-E(X)E(Y)
$$

### **相関係数** (確率変数X, Y)

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

### 不変分散

$$
U^2 = \frac{1}{n-1}\sum_{i=1}^n(x_i-\bar{x})^2
$$
 

### 標本分散

$$
S^2 = \frac{1}{n}\sum_{i=1}^n(x_i-\bar{x})^2
$$

### 二項分布
(Pの確率をn回試行した時に、x回目で起こる確率)

$$
P(X=x) = \frac{n!}{x!(n-x)!}p^x(1-p)^{n-x}
$$

#### **期待値**と**分散**

$$
E(X)=np, \qquad V(X)=np(1-p)
$$

### ポアソン分布
離散確率分布  
ある出来事が一定時間内に一定の回数($\lambda$)回起こる時の確率分布

$$
P(X=x) = \frac{e^{-\lambda}・\lambda^x}{x!}\qquad(x=0,1,2,・・・)
$$

### 幾何分布
結果が2択であるような試行を繰り返して、初めて成功するまでの回数  
(成功するかどうか)

$$
P(X=x)=p(1-p)^{x-1} \qquad (x=1,2,・・・)
$$

#### **期待値**と**分散**

$$
E(X)=\frac{1}{p}, \qquad V(X)=\frac{1-p}{p^2}
$$

#### 参考
$$
e = \lim_{x\to0}(1+x)^{\frac{1}{x}}
$$

## 区間推定

### 標準偏差
$\sigma$:母分散、n:標本数
$$
\frac{\sigma}{\sqrt{n}}
$$

### 母平均の推定（母分散が既知, 95%信頼区間）

$$
\bar{X} - 1.96\times\frac{\sigma}{\sqrt{n}}\le\mu\le\bar{X} + 1.96\times\frac{\sigma}{\sqrt{n}}
$$

### 母平均の推定（母分散が未知, 小標本）
t分布を使う

### 母平均の推定（母分散が既知, 大標本）

$$
\bar{X} - 1.96\times\frac{U}{\sqrt{n}}\le\mu\le\bar{X} + 1.96\times\frac{U}{\sqrt{n}}
$$

## 仮説検定
- 母分散が**既知**の時

母集団が$N(\mu,\sigma^2)$に従い、標本の大きさがnの時

$$
\bar{X}\qquad〜\qquad N(\mu, \frac{\sigma^2}{n}) \qquad のとき
$$

$\sigma^2$:母分散

$$
Z=\frac{\bar{X}-\mu}{\sqrt{\frac{\sigma^2}{n}}}\qquad〜\qquad N(0, 1)
$$
 
- 母分散が**未知**の場合

$U^2$:不変分散

$$
Z=\frac{\bar{X}-\mu}{\sqrt{\frac{U^2}{n}}}\qquad〜\qquad t(n-1)
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
最初、V(s)を適当に決めて、$V_0=0$とする。