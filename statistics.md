# 統計関係

## 慣例
xは $\mathbb{R}$ に属する

$$
x \in \mathbb{R}
$$

## 確率

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

相関係数を求めるにはまず共分散を求め、共分散から単位の影響を排除して求める

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
P(A|B) = \frac{P(A)P(B|A)}{P(B)}
$$

この式より導くことが出来る。

$$
p(A,B)=p(B|A)p(A)=p(A|B)p(B)
$$

### 期待値と分散

#### 期待値

$$
S_{x}^2=\frac{1}{n}\sum_{i=1}^{n}x_iy_i-\bar{x}\bar{y}
$$

#### 離散型確率変数の**期待値**

$$
E(X+Y)=E(X)+E(Y)
$$

$$
E(aX+Y)=aE(X)+E(Y)
$$

$$
E(XY)=E(X)E(Y) \qquad XとYは独立のとき
$$

#### 離散型確率変数の**分散**

$$
V(aX + b) = a^2V(X)
$$

$$
V(X+Y) = V(X) + V(Y) \qquad XとYは独立のとき
$$


$$
V(X) = E(X^2) - \{E(X)\}^2
$$

#### 分散と共分散の関係

$$
V(X+Y) = V(X) + V(Y) + 2*Cov(X, Y)
$$

### **共分散** (**確率変数** X, Y)

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

### 不偏分散

$$
U^2 = \frac{1}{n-1}\sum_{i=1}^n(x_i-\bar{x})^2
$$
 

### 標本分散

$$
S^2 = \frac{1}{n}\sum_{i=1}^n(x_i-\bar{x})^2
$$

## 確率分布

### ベルヌーイ分布

0と1の2つの値

$$
E(x)=p, \qquad V(x)=p(1-p)
$$

### 二項分布
pの確率をn回試行した時に、x回目で起こる確率P

$$
P(X=x) = \frac{n!}{x!(n-x)!}p^x(1-p)^{n-x}
$$

こっちのほうが覚えやすいかも。

$$
{}_n \mathrm{C}_xp^x(1-p)^{n-x}
$$

#### **期待値**と**分散**

$$
E(X)=np, \qquad V(X)=np(1-p)
$$

### ポアソン分布
離散確率分布  
ある出来事が一定時間内に一定の回数( $\lambda$ )回起こる時の確率分布

$$
P(X=x) = \frac{e^{-\lambda}・\lambda^x}{x!}\qquad(x=0,1,2,・・・)
$$

### 幾何分布
結果が2択であるような試行を繰り返して、**初めて**成功するまでの回数  
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

### 大数の法則

$$
\lim_{n\to∞}P(|\bar{X}-\mu|>\epsilon)=0
$$

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

- $U^2$:不偏分散
- t分布(1.96 -> t分布表より求めた確率へ変更)

### 母平均の推定（母分散が未知, 大標本, 95%信頼区間）

- $U^2$:不偏分散
- 中心極限定理

$$
\bar{X} - 1.96\times\frac{U}{\sqrt{n}}\le\mu\le\bar{X} + 1.96\times\frac{U}{\sqrt{n}}
$$

### 母分散の区間推定

$$
\frac{(n-1)U^2}{\sigma^2}\qquad〜\qquad \chi^2(n-1)
$$

## 仮説検定

### 母平均の仮説検定(母分散が**既知**)

母集団が $N(\mu,\sigma^2)$ に従い、標本の大きさがnの時

$$
\bar{X}\qquad〜\qquad N(\mu, \frac{\sigma^2}{n}) \qquad のとき
$$

$\sigma^2$:母分散

$$
Z=\frac{\bar{X}-\mu}{\sqrt{\frac{\sigma^2}{n}}}\qquad〜\qquad N(0, 1)
$$
 
### 母平均の仮説検定(母分散が**未知**、小標本)

- $U^2$:不偏分散
- t分布

$$
T=\frac{\bar{X}-\mu}{\sqrt{\frac{U^2}{n}}}\qquad〜\qquad t(n-1)
$$

### 母平均の仮説検定(母分散が**未知**、大標本)

$$
Z=\frac{\bar{X}-\mu}{\sqrt{\frac{U^2}{n}}}\qquad〜\qquad N(0, 1)
$$

## 母比率の(差の)検定

### 母比率の検定(大標本)

- 標本比率 $\frac{X}{n}$
- $n\to∞$の時、$N(p,\frac{p(1-p)}{n})に従う$

$$
Z= \frac{\frac{X}{n}-p}{\sqrt{\frac{p(1-p)}{n}}}\qquad〜\qquad N(0, 1)
$$

### 母比率の**差の**検定(大標本)

### 母平均の差の検定

#### 対応あり、2群

$$
T= \frac{\bar{X}}{\sqrt{\frac{U^2}{n}}}\qquad〜\qquad t(n-1)
$$

#### 対応なし、2群、母分散既知

$$
\frac{\bar{X}-\bar{Y}}{\sqrt{\frac{\sigma_1^2}{n_1}+\frac{\sigma_2^2}{n_2}}}
$$

#### 対応なし、2群、母分散未知(大標本)

$$
\frac{\bar{X}-\bar{Y}}{\sqrt{\frac{U_1^2}{n_1}+\frac{U_2^2}{n_2}}}\qquad〜\qquad N(0, 1)
$$

#### 対応なし、2群、母分散未知(小標本、等分散)

$$
\frac{\bar{X}-\bar{Y}}{\sqrt{\hat{U^2}(\frac{1}{n_1}+\frac{1}{n_2}})}\qquad〜\qquad N(0, 1)
$$

$\hat{U}^2$ はプールした分散

$$
\hat{U}^2=\frac{\sum_{k=1}^{n_1}(X_k-\bar{X})^2+\sum_{k=1}^{n_2}(Y_k-\bar{Y})^2}{n_1+n_2-2}
$$

### 等分散の検定

2群が独立という仮定のもと

- $H_0$: $\sigma_1^2 = \sigma_2^2$
- $H_1$: $\sigma_1^2$ > $\sigma_2^2$, $\sigma_1^2$ < $\sigma_2^2$, $\sigma_1^2 \ne \sigma_2^2$
- 母集団 N($\mu_1$, $\sigma_1^2$), N($\mu_2$, $\sigma_2^2$)
- F分布

$$
F = \frac{U_2^2}{U_1^2}\qquad〜\qquad F(n_2-1, n_1-1)
$$

### 適合度検定
実験データの分布と特定の理論が合っていないことを示す検定

$$
\sum_{i=1}^{n}\frac{(X_i-np_i)^2}{np_i}\qquad〜\qquad \chi^2(k-1)
$$

### 独立性の検定
2要因が独立でないことを示す

$$
\sum\frac{(実測度数-期待度数)^2}{期待度数}=\sum\frac{(X_i-nP_i)^2}{nP_i}\qquad〜\qquad \chi^2(df)
$$

- df = (m – 1) × (n – 1)
- クロス表（分割表）
- 観測度数と理論度数(期待度数)を比較する
- (母比率の差の検定)

### 分散分析
基本3群以上の母平均の差の検定

m: 水準の数、N: 標本の数

$$
\frac{水準間平均平方}{残差平均平方}\qquad〜\qquad F(m-1,N-m)
$$

- 分散分析表
- F値を求める
- Pr(>F)値と有意水準0.05などと比較する
- 一元配置分散分析

## 回帰分析
p値：t()を用いた検定結果
### 単回帰分析

$$
T=\frac{推定値-真の値}{標準偏差}\qquad 〜\qquad t(n-1-1)
$$

#### 残差平方和

$$
\sum_{i=1}^{n}\hat{\mu}_i^2
$$

#### 不偏推定量

$$
E[\frac{1}{n-2}\sum_{i=1}^{n}\hat{\mu}_i^2]=\sigma^2
$$

### 重回帰分析

$$
T=\frac{推定値-真の値}{標準偏差}\qquad 〜\qquad t(n-p-1)
$$

#### 決定係数

$$
R^2=1-\frac{残差平方和}{偏差平方和}
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
最初、V(s)を適当に決めて、 $V_0=0$ とする。