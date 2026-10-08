# Homework 1 Solutions

## 2.1 Moments and Covariance of Uniform Random Variables (20 points)

Given:

- $X \sim \operatorname{Uniform}[0,10]$
- $Y \sim \operatorname{Uniform}[2,8]$
- $X$ and $Y$ are independent
- $Z=X+Y$

**1. Calculate $\mu_X=E[X]$**

For a uniform distribution on $[a,b]$, the mean is

$$
E[X]=\frac{a+b}{2}=\frac{0+10}{2}=5.
$$

Therefore,

$$
\boxed{\mu_X=5}.
$$

**2. Calculate $\mu_Z=E[Z]$**

Since $Z=X+Y$,

$$
E[Z]=E[X+Y]=E[X]+E[Y].
$$

We already have $E[X]=5$, and

$$
E[Y]=\frac{2+8}{2}=5.
$$

Thus,

$$
\boxed{\mu_Z=E[Z]=5+5=10}.
$$

**3. Calculate $\sigma_X^2=\operatorname{Var}(X)$**

For a uniform distribution on $[a,b]$,

$$
\operatorname{Var}(X)=\frac{(b-a)^2}{12}.
$$

Hence,

$$
\boxed{
\sigma_X^2
=\frac{(10-0)^2}{12}
=\frac{100}{12}
=\frac{25}{3}
}.
$$

**4. Calculate $\sigma_Z^2=\operatorname{Var}(Z)$**

Since $X$ and $Y$ are independent,

$$
\operatorname{Var}(Z)
=\operatorname{Var}(X+Y)
=\operatorname{Var}(X)+\operatorname{Var}(Y).
$$

Also,

$$
\operatorname{Var}(Y)
=\frac{(8-2)^2}{12}
=\frac{36}{12}
=3.
$$

Therefore,

$$
\boxed{
\sigma_Z^2
=\frac{25}{3}+3
=\frac{34}{3}
}.
$$

**5. Calculate $\operatorname{Cov}(X,Z)$**

Recall that

$$
\operatorname{Cov}(X,Z)=E[XZ]-E[X]E[Z].
$$

First,

$$
\begin{aligned}
E[XZ]
&=E[X(X+Y)] \\
&=E[X^2+XY] \\
&=E[X^2]+E[XY].
\end{aligned}
$$

Because $X$ and $Y$ are independent,

$$
E[XY]=E[X]E[Y]=5\cdot 5=25.
$$

For a uniform random variable on $[a,b]$,

$$
E[X^2]=\frac{a^2+ab+b^2}{3}.
$$

Therefore,

$$
E[X^2]
=\frac{0^2+0\cdot 10+10^2}{3}
=\frac{100}{3},
$$

and

$$
E[XZ]=\frac{100}{3}+25=\frac{175}{3}.
$$

It follows that

$$
\begin{aligned}
\operatorname{Cov}(X,Z)
&=E[XZ]-E[X]E[Z] \\
&=\frac{175}{3}-(5\cdot 10) \\
&=\frac{25}{3}.
\end{aligned}
$$

Alternatively,

$$
\begin{aligned}
\operatorname{Cov}(X,Z)
&=\operatorname{Cov}(X,X+Y) \\
&=\operatorname{Var}(X)+\operatorname{Cov}(X,Y) \\
&=\frac{25}{3}+0 \\
&=\frac{25}{3}.
\end{aligned}
$$

Thus,

$$
\boxed{\operatorname{Cov}(X,Z)=\frac{25}{3}}.
$$

In summary,

$$
\boxed{
\mu_X=5,\qquad
\mu_Z=10,\qquad
\sigma_X^2=\frac{25}{3},\qquad
\sigma_Z^2=\frac{34}{3},\qquad
\operatorname{Cov}(X,Z)=\frac{25}{3}
}.
$$

## 2.2 Eigenpairs of Inverse and Shifted-Inverse Matrices (20 points)

**(a) (10 points)**

Suppose that $A$ is nonsingular and $(\lambda,x)$ is an eigenpair of $A$. Show that $(\lambda^{-1},x)$ is an eigenpair of $A^{-1}$.

**Proof.** Since $A$ is nonsingular, $\lambda\ne 0$. Otherwise, $Ax=0$ with $x\ne 0$ would imply that $A$ is singular.

Given $Ax=\lambda x$, multiply both sides on the left by $A^{-1}$:

$$
\begin{aligned}
A^{-1}Ax&=A^{-1}(\lambda x), \\
x&=\lambda A^{-1}x.
\end{aligned}
$$

Since $\lambda\ne 0$,

$$
A^{-1}x=\frac{1}{\lambda}x=\lambda^{-1}x.
$$

Thus, $x$ is an eigenvector of $A^{-1}$ with eigenvalue $\lambda^{-1}$, so $(\lambda^{-1},x)$ is an eigenpair of $A^{-1}$. $\square$

**(b) (10 points)**

For any scalar $\alpha$ that is not an eigenvalue of $A$, show that $x$ is an eigenvector of $A$ if and only if $x$ is an eigenvector of $(A-\alpha I)^{-1}$.

**Proof.**

**Forward direction.** Suppose $x$ is an eigenvector of $A$, so $Ax=\lambda x$ for some eigenvalue $\lambda$. Then

$$
\begin{aligned}
(A-\alpha I)x
&=Ax-\alpha x \\
&=\lambda x-\alpha x \\
&=(\lambda-\alpha)x.
\end{aligned}
$$

Because $\alpha$ is not an eigenvalue of $A$, $\lambda-\alpha\ne 0$. Multiplying by $(A-\alpha I)^{-1}$ gives

$$
x=(\lambda-\alpha)(A-\alpha I)^{-1}x,
$$

and hence

$$
(A-\alpha I)^{-1}x=\frac{1}{\lambda-\alpha}x.
$$

Therefore, $x$ is an eigenvector of $(A-\alpha I)^{-1}$.

**Reverse direction.** Suppose $x$ is an eigenvector of $(A-\alpha I)^{-1}$, so

$$
(A-\alpha I)^{-1}x=\mu x
$$

for some $\mu\ne 0$. Multiplying by $A-\alpha I$ gives

$$
x=\mu(A-\alpha I)x,
$$

so

$$
(A-\alpha I)x=\frac{1}{\mu}x.
$$

Therefore,

$$
Ax-\alpha x=\frac{1}{\mu}x,
$$

which yields

$$
Ax=\left(\alpha+\frac{1}{\mu}\right)x.
$$

Thus, $x$ is an eigenvector of $A$. This proves the equivalence. $\square$

## 2.3 Maximum Likelihood Estimation (20 points)

A random variable has probability density function

$$
f(x;\theta)=(\theta+1)x^\theta,
\qquad 0<x<1,\quad \theta\in\mathbb{R}.
$$

Given samples $X_1,\ldots,X_n$, derive the maximum likelihood estimator of $\theta$.

The likelihood function is

$$
\begin{aligned}
L(\theta)
&=\prod_{i=1}^{n}f(x_i;\theta) \\
&=\prod_{i=1}^{n}(\theta+1)x_i^\theta \\
&=(\theta+1)^n\prod_{i=1}^{n}x_i^\theta.
\end{aligned}
$$

The log-likelihood function is

$$
\ell(\theta)
=\ln L(\theta)
=n\ln(\theta+1)+\theta\sum_{i=1}^{n}\ln x_i.
$$

Differentiating with respect to $\theta$ gives

$$
\frac{d\ell}{d\theta}
=\frac{n}{\theta+1}+\sum_{i=1}^{n}\ln x_i.
$$

Set the derivative equal to zero:

$$
\begin{aligned}
\frac{n}{\theta+1}+\sum_{i=1}^{n}\ln x_i&=0, \\
\frac{n}{\theta+1}&=-\sum_{i=1}^{n}\ln x_i, \\
\theta+1&=-\frac{n}{\sum_{i=1}^{n}\ln x_i}, \\
\theta&=-1-\frac{n}{\sum_{i=1}^{n}\ln x_i}.
\end{aligned}
$$

The second derivative is

$$
\frac{d^2\ell}{d\theta^2}
=-\frac{n}{(\theta+1)^2}<0,
$$

so the critical point is a maximum.

The density is valid for $\theta>-1$. Since $x_i\in(0,1)$, each $\ln x_i<0$, and therefore

$$
-\frac{n}{\sum_{i=1}^{n}\ln x_i}>0.
$$

Thus, the estimate satisfies the parameter constraint, and the maximum likelihood estimator is

$$
\boxed{
\widehat{\theta}_{\mathrm{MLE}}
=-1-\frac{n}{\sum_{i=1}^{n}\ln X_i}
}.
$$

Equivalently,

$$
\widehat{\theta}_{\mathrm{MLE}}
=-1-\frac{1}{\frac{1}{n}\sum_{i=1}^{n}\ln X_i}
=-1-\frac{1}{\ln(\overline{X}_G)},
$$

where

$$
\overline{X}_G
=\left(\prod_{i=1}^{n}X_i\right)^{1/n}
$$

is the geometric mean.

## 2.4 Entropy and Mutual Information (20 points)

The joint probability mass function is

$$
p(x,y)
=\frac{1}{25}
\begin{pmatrix}
1 & 1 & 1 & 1 & 1 \\
2 & 1 & 2 & 0 & 0 \\
2 & 0 & 1 & 1 & 1 \\
0 & 3 & 0 & 2 & 0 \\
0 & 0 & 1 & 1 & 3
\end{pmatrix}.
$$

Summing the rows and columns gives the marginal distributions

$$
p_X(x)=\frac{1}{5},
\qquad
p_Y(y)=\frac{1}{5}
\quad\text{for all }x,y.
$$

Therefore,

$$
H(X)=\log_2 5,
\qquad
H(Y)=\log_2 5.
$$

For the joint entropy, let $n_{xy}\in\{0,1,2,3\}$ denote the integer entries in the matrix. There are 8 zeros, 11 ones, 4 twos, and 2 threes. Hence,

$$
\begin{aligned}
H(X,Y)
&=-\sum_{x,y}p(x,y)\log_2 p(x,y) \\
&=\log_2 25-\frac{8}{25}-\frac{6}{25}\log_2 3.
\end{aligned}
$$

The conditional entropies are

$$
\begin{aligned}
H(X\mid Y)
&=H(X,Y)-H(Y) \\
&=\log_2 5-\frac{8}{25}-\frac{6}{25}\log_2 3,
\end{aligned}
$$

and

$$
\begin{aligned}
H(Y\mid X)
&=H(X,Y)-H(X) \\
&=\log_2 5-\frac{8}{25}-\frac{6}{25}\log_2 3.
\end{aligned}
$$

The mutual information is

$$
\begin{aligned}
I(X;Y)
&=H(X)+H(Y)-H(X,Y) \\
&=\frac{8}{25}+\frac{6}{25}\log_2 3.
\end{aligned}
$$

Numerically,

$$
\begin{aligned}
H(X)&\approx 2.3219, &
H(Y)&\approx 2.3219, \\
H(X\mid Y)&\approx 1.6215, &
H(Y\mid X)&\approx 1.6215, \\
I(X;Y)&\approx 0.7004.
\end{aligned}
$$

## 2.5 Umbrella Markov Chain (10 points)

**(i)**

Let $X_n$ be the number of umbrellas at Jim's current location at the start of trip $n$.

The weather on each trip is independent, with rain probability $p$. The next state $X_{n+1}$ depends only on $X_n$ and whether it rains on trip $n$:

- If $X_n=i\ge 1$ and it rains, with probability $p$, Jim takes one umbrella, so $X_{n+1}=5-i$.
- If $X_n=i\ge 1$ and it does not rain, with probability $1-p$, then $X_{n+1}=4-i$.
- If $X_n=0$, then $X_{n+1}=4$ whether or not it rains; if it rains, Jim gets wet.

Thus, $\{X_n\}$ is a Markov chain on the state space $\{0,1,2,3,4\}$. With rows and columns ordered as $0,1,2,3,4$, its transition matrix is

$$
P=
\begin{pmatrix}
0 & 0 & 0 & 0 & 1 \\
0 & 0 & 0 & 1-p & p \\
0 & 0 & 1-p & p & 0 \\
0 & 1-p & p & 0 & 0 \\
1-p & p & 0 & 0 & 0
\end{pmatrix}.
$$

**(ii)**

Initially, $X_1=2$ at home on the morning of day 1, and $p=0.2$.

On the morning trip, Jim has two umbrellas available. Whether or not it rains, he does not get wet. After that trip, $X_2=3$ if it rained and $X_2=2$ if it did not rain.

In either case, at least one umbrella is available for the evening trip. Therefore, even if it rains in the evening, Jim can take an umbrella.

Thus, the probability that Jim gets wet during day 1 is

$$
\boxed{0}.
$$

## 2.6 KL-Divergence Limit (10 points)

The distribution $D_n^{(\alpha,\beta)}$ is defined by

$$
D_n^{(\alpha,\beta)}(1)
=1-\left(\frac{\log\alpha}{\log n}\right)^\beta,
$$

and, for $x=2,\ldots,n+1$,

$$
D_n^{(\alpha,\beta)}(x)
=\frac{1}{n}
\left(\frac{\log\alpha}{\log n}\right)^\beta,
$$

with $D_n^{(\alpha,\beta)}(x)=0$ otherwise.

For $\nu=(1,0,0,\ldots)$,

$$
\begin{aligned}
D_{\mathrm{KL}}\left(\nu\middle\|D_n^{(\alpha,\beta)}\right)
&=\sum_x\nu(x)
\log\frac{\nu(x)}{D_n^{(\alpha,\beta)}(x)} \\
&=-\log\left[
1-\left(\frac{\log\alpha}{\log n}\right)^\beta
\right].
\end{aligned}
$$

Let

$$
\epsilon_n
=\left(\frac{\log\alpha}{\log n}\right)^\beta.
$$

As $n\to\infty$, $\log n\to\infty$, so $\epsilon_n\to 0$. Using

$$
-\log(1-\epsilon_n)\sim\epsilon_n\to 0,
$$

we obtain

$$
\boxed{
\lim_{n\to\infty}
D_{\mathrm{KL}}\left(\nu\middle\|D_n^{(\alpha,\beta)}\right)
=0
}.
$$
