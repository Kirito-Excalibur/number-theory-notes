# Module 2 — Congruences & Primitive Roots

## Congruence

**Definition.** Given integers $a, b, m$ with $m > 0$, we say that $a$ is *congruent to $b$ modulo $m$*, and write $a \equiv b \pmod m$, if $m \mid a - b$.

**Examples.**

- $19 \equiv 7 \pmod{12}$; $\ 1 \equiv -1 \pmod 2$.

- $n \equiv 0 \pmod 2$ if $n$ is even; $n \equiv 1 \pmod 2$ if $n$ is odd.

- $a \equiv b \pmod 1$ for all $a, b \in \mathbb{Z}$.

- $a \equiv b \pmod m$ $\Rightarrow a \equiv b \pmod d$ for $d \mid m$.

- $a \equiv 0 \pmod m \iff m \mid a$; $\ a \equiv b \pmod m$ $\iff a - b \equiv 0 \pmod m$.

When $a \not\equiv b \pmod m$, we say $a$ and $b$ are *incongruent* mod $m$.

!!! abstract "Lemma"
    Congruence modulo $m$ is an equivalence relation on $\mathbb{Z}$.

*Proof.*

- **Reflexive:** $a \equiv a \pmod m$ for all $a \in \mathbb{Z}$.

- **Symmetric:** $a \equiv b \pmod m$ $\Rightarrow m \mid a - b$ $\Rightarrow m \mid b - a$ $\Rightarrow b \equiv a \pmod m$.

- **Transitive:** $a \equiv b \pmod m$ and $b \equiv c \pmod m$ $\Rightarrow m \mid a - b$ and $m \mid b - c$ $\Rightarrow m \mid (a - b) + (b - c)$ $\Rightarrow a \equiv c \pmod m$. $\blacksquare$

Thus the equivalence relation yields a partition of $\mathbb{Z}$. Each of the parts is called a *residue class*. For $a \in \mathbb{Z}$, the residue class of $a$ is denoted by $\bar a$.

!!! abstract "Lemma"
    There exist exactly $m$ distinct residue classes, given by $\bar 0, \bar 1, \ldots, \overline{m-1}$.

*Proof.* If $0 \le a, b \le m - 1$ and $a \ne b$, then $m \nmid a - b$ $\Rightarrow a \not\equiv b \pmod m$. So all the residue classes $\bar 0, \bar 1, \ldots, \overline{m-1}$ are distinct.

Now suppose $a \in \mathbb{Z}$. By the division algorithm, $a = qm + r$ where $0 \le r < m$, so $a \equiv r \pmod m$ $\Rightarrow \bar a = \bar r$ (the classes $\bar a$ and $\bar r$ are the same), i.e. $\bar a \in \{\bar 0, \bar 1, \ldots, \overline{m-1}\}$. This finishes the proof. $\blacksquare$

Denote the set $\{\bar 0, \bar 1, \ldots, \overline{m-1}\}$ by $\mathbb{Z}_m$ or $\mathbb{Z}/m\mathbb{Z}$. Then $\mathbb{Z}_m$ is an abelian group under the operation $\bar a + \bar b = \overline{a + b}$.

!!! abstract "Proposition"
    Let $a \equiv b \pmod m$ and $\alpha \equiv \beta \pmod m$. Then

    1. $ax + \alpha y \equiv bx + \beta y \pmod m$.

    2. $a\alpha \equiv b\beta \pmod m$.

    3. $a^n \equiv b^n \pmod m$ for all $n \ge 1$.

    4. $f(a) \equiv f(b) \pmod m$ when $f(x) \in \mathbb{Z}[x]$.

*Proof.* Exercise.

## Linear Congruence and Chinese Remainder Theorem

**Motivation.** Given $f(x) \in \mathbb{Z}[x]$, we are interested in finding integer solutions to $f(x) = 0$. But this is difficult in general. Instead, if we consider $f(x)$ in $\mathbb{Z}_m[x]$ and ask for solutions in $\mathbb{Z}_m$ to $f(x) = 0$, it is relatively easier, as $\mathbb{Z}_m$ is a finite set.

- If $f$ has a solution in $\mathbb{Z}$, then $f$ has a solution in $\mathbb{Z}_m$ for every $m$.

- Thus $f(x) = 0$ in $\mathbb{Z}_m[x]$ gives information about *local* solutions (centered at $m$).

- This turns an infinite problem into a sequence of finite problems. This is a "global to local" viewpoint.

Linear congruences are of the form $ax \equiv b \pmod m$, or equivalently $ax = b$ in $\mathbb{Z}_m[x]$. Our interest is to find solutions of $ax - b = 0$ in $\mathbb{Z}_m$.

**Example.** $2x \equiv 3 \pmod 4$ has no solution, as $2x - 3$ is odd for every value of $x$, so $4 \nmid 2x - 3$.

!!! abstract "Theorem"
    Let $\gcd(a, m) = 1$. Then the equation $ax \equiv b \pmod m$ has exactly one solution in $\mathbb{Z}_m$.

*Proof.* $\mathbb{Z}_m = \{\bar 0, \bar 1, \ldots, \overline{m-1}\}$. Since $\gcd(a, m) = 1$, $\mathbb{Z}_m = \{\bar 0, \bar a, \ldots, \overline{a(m-1)}\}$ (by an exercise in the assignment). Since $\bar b \in \mathbb{Z}_m$, there exists a unique $\bar r \in \mathbb{Z}_m$ such that $\bar a \bar r = \bar b$. So $\bar r$ is the unique solution to $ax \equiv b \pmod m$. $\blacksquare$

!!! abstract "Theorem"
    Let $d = \gcd(a, m)$. Then the equation $ax \equiv b \pmod m$ has a solution if and only if $d \mid b$. Furthermore, in this case, the equation has exactly $d$ incongruent solutions.

*Proof.* Solving $ax \equiv b \pmod m$ $\iff$ solving $ax - b = my$ $\iff$

$$ax - my = b. \tag{1}$$

So $ax \equiv b \pmod m$ has a solution $\iff$ (1) has a solution $\iff d \mid b$.

If $(x_0, y_0)$ is a particular solution to (1), then all the solutions are given by

$$\left\{\left(x_0 + \frac{m}{d} t,\ y_0 - \frac{a}{d} t\right) \;\middle|\; t \in \mathbb{Z}\right\}.$$

Thus for any $t \in \mathbb{Z}$, $\overline{x_0 + \frac{m}{d} t}$ is a solution to $ax \equiv b \pmod m$.

*Claim:* $S = \left\{\overline{x_0 + \frac{m}{d} t} \;\middle|\; 0 \le t < d\right\}$ is the complete set of solutions of $ax \equiv b \pmod m$.

- If $t \ge d$, write $t = dq + r$ with $0 \le r < d$. Then

    $$x_0 + \frac{m}{d} t \equiv x_0 + mq + \frac{m}{d} r \equiv x_0 + \frac{m}{d} r \pmod m,$$

    which lies in $S$.

- If $0 \le t_1, t_2 < d$ with $t_1 \ne t_2$, then $x_0 + \frac{m}{d} t_1$ and $x_0 + \frac{m}{d} t_2$ are incongruent modulo $m$. Indeed,

    $$x_0 + \tfrac{m}{d} t_1 \equiv x_0 + \tfrac{m}{d} t_2 \pmod m \Rightarrow \tfrac{m}{d} t_1 \equiv \tfrac{m}{d} t_2 \pmod m \Rightarrow t_1 \equiv t_2 \pmod d \Rightarrow t_1 = t_2,$$

    a contradiction. (Apply the cancellative law with $\gcd(m, \frac{m}{d}) = \frac{m}{d}$.)

This completes the proof. $\blacksquare$

**Example.** $18x \equiv 30 \pmod{42}$. Here $\gcd(18, 42) = 6$ and $6 \mid 30$, so the equation has a solution. Using the Euclidean algorithm, check that $x = 4$ is a solution. Then $\{4 + 7t \mid 0 \le t < 6\}$ is the complete set of solutions.

!!! note "Remark"
    The particular solution $x_0$ is also a solution to $\frac{a}{d} x \equiv \frac{b}{d} \pmod{\frac{m}{d}}$; i.e., $x \equiv x_0 \pmod{\frac{m}{d}}$ is the unique solution to $\frac{a}{d} x \equiv \frac{b}{d} \pmod{\frac{m}{d}}$.

### Systems of linear congruences

Suppose we want to solve the system of linear congruences

$$
\begin{aligned}
a_1 x &\equiv b_1 \pmod{m_1} \\
a_2 x &\equiv b_2 \pmod{m_2} \\
&\;\;\vdots \\
a_r x &\equiv b_r \pmod{m_r}
\end{aligned}
$$

The system admits no solution unless each individual congruence is solvable. Let $d_k = \gcd(a_k, m_k)$ with $d_k \mid b_k$. This leads us to solve the system

$$
(*) \qquad
\begin{aligned}
x &\equiv c_1 \pmod{n_1} \\
&\;\;\vdots \\
x &\equiv c_r \pmod{n_r}
\end{aligned}
$$

where $n_k = \dfrac{m_k}{d_k}$.

Now consider the situation where $n_1, \ldots, n_r$ are not pairwise prime; WLOG assume $\gcd(n_1, n_2) = d_{12} > 1$. Then a common solution of $x \equiv c_1 \pmod{n_1}$, $x \equiv c_2 \pmod{n_2}$ will be a solution to $x \equiv c_1 \pmod{d_{12}}$ and $x \equiv c_2 \pmod{d_{12}}$, so $c_1 \equiv c_2 \pmod{d_{12}}$. This is a strong condition on the system $(*)$.

The situation is better if we assume $d_{12} = 1$, i.e. all of $n_1, \ldots, n_r$ are pairwise coprime. Thus we have the following system of linear congruences:

$$
(**) \qquad
\begin{aligned}
x &\equiv c_1 \pmod{n_1} \\
&\;\;\vdots \\
x &\equiv c_r \pmod{n_r}
\end{aligned}
$$

with $\gcd(n_i, n_j) = 1$ for $i \ne j$.

!!! abstract "Chinese Remainder Theorem"
    The system of linear congruences $(**)$ has a solution, and the solution is unique modulo $n_1 \cdots n_r$.

*Construction of the solution.* Let $n = n_1 n_2 \cdots n_r$ and $N_k = \dfrac{n}{n_k}$.

- Clearly $N_k x \equiv 1 \pmod{n_k}$ has a unique solution, say $x_k$; i.e. $N_k x_k \equiv 1 \pmod{n_k}$ $\Rightarrow c_k N_k x_k \equiv c_k \pmod{n_k}$.

- Let $x = c_1 N_1 x_1 + \cdots + c_r N_r x_r$. Then $x \equiv c_k N_k x_k \equiv c_k \pmod{n_k}$ for each $k$.

- Therefore $x \pmod{n_1 \cdots n_r}$ is the unique solution to $(**)$.

**Example.** Solve

$$
\begin{aligned}
x &\equiv 2 \pmod 3 \\
x &\equiv 3 \pmod 5 \\
x &\equiv 2 \pmod 7
\end{aligned}
$$

*Solution.* $n = 3 \cdot 5 \cdot 7 = 105$; $N_1 = 35$, $N_2 = 21$, $N_3 = 15$. Now we solve:

| Congruence | Solution |
| --- | --- |
| $35x \equiv 1 \pmod 3$ | $x_1 = 2$ |
| $21x \equiv 1 \pmod 5$ | $x_2 = 1$ |
| $15x \equiv 1 \pmod 7$ | $x_3 = 1$ |

So

$$
\begin{aligned}
x &= c_1 N_1 x_1 + c_2 N_2 x_2 + c_3 N_3 x_3 \\
&= 2 \cdot 35 \cdot 2 + 3 \cdot 21 \cdot 1 + 2 \cdot 15 \cdot 1 \\
&= 233.
\end{aligned}
$$

Therefore the system has the unique solution $233 \equiv 23 \pmod{105}$.

## Fermat's Little Theorem

!!! abstract "Theorem (Euler–Fermat)"
    If $\gcd(a, m) = 1$, then $a^{\varphi(m)} \equiv 1 \pmod m$.

*Proof.* Let $S = \{\bar k \in \mathbb{Z}_m \mid \gcd(k, m) = 1\}$. Then

$$
\begin{aligned}
\bar k \in S &\iff \gcd(k, m) = 1 \\
&\iff \gcd(ak, m) = 1 \quad [\because \gcd(a, m) = 1] \\
&\iff \overline{ak} \in S.
\end{aligned}
$$

Thus if $S = \{\bar k_1, \ldots, \bar k_{\varphi(m)}\}$, then $S = \{\overline{ak_1}, \ldots, \overline{ak_{\varphi(m)}}\}$. Multiplying out both descriptions of $S$, with $P = k_1 k_2 \cdots k_{\varphi(m)}$:

$$
\begin{aligned}
P &\equiv (ak_1)(ak_2) \cdots (ak_{\varphi(m)}) \\
&\equiv a^{\varphi(m)} P \pmod m.
\end{aligned}
$$

Since $\gcd(P, m) = 1$, we can cancel $P$ to get $a^{\varphi(m)} \equiv 1 \pmod m$. $\blacksquare$

**Corollary.** Let $p$ be a prime. Then

1. If $p \nmid a$, then $a^{p-1} \equiv 1 \pmod p$.

2. $a^p \equiv a \pmod p$ for all $a \in \mathbb{Z}$.

**Corollary.** If $\gcd(a, m) = 1$, then the solution to $ax \equiv b \pmod m$ is given by

$$x \equiv b\, a^{\varphi(m) - 1} \pmod m.$$

**Exercise.**

1. Solve $5x \equiv 3 \pmod{24}$.

2. Solve $25x \equiv 15 \pmod{120}$.

## Polynomial Congruence modulo $p$

Let

$$f(x) = c_0 + c_1 x + \cdots + c_n x^n \in \mathbb{Z}[x].$$

Call this polynomial $(*)$.

Our interest is to find solutions of $f(x) \equiv 0 \pmod p$, where $p$ is a prime.

!!! abstract "Theorem (Lagrange)"
    Let $p$ be a prime and $f$ a polynomial as in $(*)$ such that $p \nmid c_n$ ($\iff c_n \not\equiv 0 \pmod p$). Then the equation $f(x) \equiv 0 \pmod p$ has at most $n$ solutions modulo $p$.

**Corollary.** If $f$, as in $(*)$, is a polynomial of degree $n$ and if $f(x) \equiv 0 \pmod p$ has more than $n$ solutions, then $p \mid c_i$ for $0 \le i \le n$.

**Corollary.** Let $p$ be a prime number and $d \mid p - 1$. Then $x^d \equiv 1 \pmod p$ has exactly $d$ solutions in $\mathbb{Z}_p$.

*Proof.* Let $p - 1 = dk$. Then

$$x^{p-1} - 1 = (x^d - 1) f(x),$$

where

$$f(x) = x^{d(k-1)} + x^{d(k-2)} + \cdots + x^d + 1.$$

- $x^{p-1} - 1 \equiv 0 \pmod p$ has exactly $p - 1$ solutions in $\mathbb{Z}_p$.

- $f(x) \equiv 0 \pmod p$ has at most $d(k-1)$ roots.

- So $x^d \equiv 1 \pmod p$ has at least $(p - 1) - d(k - 1) = d$ roots.

- By Lagrange's theorem, $x^d \equiv 1 \pmod p$ has exactly $d$ roots in $\mathbb{Z}_p$. $\blacksquare$

!!! abstract "Theorem"
    For any prime $p$, all the coefficients of

    $$f(x) = (x - 1)(x - 2) \cdots (x - p + 1) - x^{p-1} + 1$$

    are divisible by $p$.

*Proof.* Let $g(x) = (x-1)(x-2)\cdots(x-p+1)$ and $h(x) = x^{p-1} - 1$. Then $f(x) = g(x) - h(x)$.

- By Fermat's little theorem, $\bar 1, \bar 2, \ldots, \overline{p-1}$ are solutions to $h(x) \equiv 0 \pmod p$.

- Evidently, $\bar 1, \bar 2, \ldots, \overline{p-1}$ are solutions to $g(x) \equiv 0 \pmod p$.

- So $\bar 1, \bar 2, \ldots, \overline{p-1}$ are solutions to $f(x) \equiv 0 \pmod p$. But the degree of $f$ is $< p - 1$. Now apply the above corollary. $\blacksquare$

!!! abstract "Wilson's Theorem"
    For any prime $p$, $(p - 1)! \equiv -1 \pmod p$.

*Proof.* The constant term of $f$, as in the previous theorem, is $(p - 1)! + 1$. By the above theorem, $(p - 1)! \equiv -1 \pmod p$. $\blacksquare$

## Primitive Roots

By Fermat's theorem we know that if $\gcd(a, n) = 1$, then $a^{\varphi(n)} \equiv 1 \pmod n$.

**Definition.** Let $n > 1$ and $\gcd(a, n) = 1$. The *order of $a$ modulo $n$* is the smallest positive integer $k$ such that $a^k \equiv 1 \pmod n$.

!!! note "Remark"
    In the above definition, the condition $\gcd(a, n) = 1$ is necessary. (Why?)

!!! abstract "Proposition"
    Assume $\gcd(a, n) = 1$ and $a$ has order $k$ modulo $n$. Then $a^h \equiv 1 \pmod n$ if and only if $k \mid h$. In particular, $k \mid \varphi(n)$.

*Proof.* By the division algorithm, $h = kq + r$ with $0 \le r < k$. Then

$$
\begin{aligned}
a^h &\equiv (a^k)^q \cdot a^r \pmod n \\
\Rightarrow\; a^r &\equiv 1 \pmod n \\
\Rightarrow\; r &= 0. \quad \blacksquare
\end{aligned}
$$

**Corollary.** If $a$ has order $k$ modulo $n$, then $a^i \equiv a^j \pmod n$ $\iff i \equiv j \pmod k$.

*Proof.* For $i \ge j$: $a^i \equiv a^j \pmod n$ $\iff a^{i-j} \equiv 1 \pmod n$ $\iff k \mid i - j$ $\iff i \equiv j \pmod k$. $\blacksquare$

**Corollary.** If $a$ has order $k$ modulo $n$, then the integers $a, a^2, \ldots, a^k$ are incongruent modulo $n$.

*Proof.* For $1 \le i, j \le k$: $a^i \equiv a^j \pmod n$ $\iff k \mid i - j$ $\iff i = j$. $\blacksquare$

!!! abstract "Proposition"
    If the integer $a$ has order $k$ modulo $n$ and $h > 0$, then $a^h$ has order $\dfrac{k}{\gcd(h, k)}$ modulo $n$.

*Proof.* Let $d = \gcd(h, k)$, so $h = dh_1$, $k = dk_1$ with $\gcd(h_1, k_1) = 1$.

- $(a^h)^{k_1} = a^{dh_1 k_1} \equiv (a^k)^{h_1} \equiv 1 \pmod n$. Let $a^h$ have order $r$ modulo $n$; then $r \mid k_1$.

- Now $(a^h)^r \equiv 1 \pmod n$ $\Rightarrow k \mid hr$ $\Rightarrow dk_1 \mid dh_1 r$ $\Rightarrow k_1 \mid h_1 r$ $\Rightarrow k_1 \mid r$ (since $\gcd(h_1, k_1) = 1$).

- Therefore $r = k_1$. $\blacksquare$

**Corollary.** Let $a$ have order $k$ modulo $n$. Then $a^h$ has order $k \iff \gcd(h, k) = 1$.

**Definition.** If $\gcd(a, n) = 1$, we say $a$ is a *primitive root* of $n$ if $a$ has order $\varphi(n)$ modulo $n$.

**Example.** 3 is a primitive root of 7.

!!! abstract "Theorem"
    Let $\gcd(a, n) = 1$, and let $a_1, \ldots, a_{\varphi(n)}$ be the positive integers less than $n$ and relatively prime to $n$. If $a$ is a primitive root of $n$, then

    $$\{\bar a, \bar a^2, \ldots, \bar a^{\varphi(n)}\} = \{\bar a_1, \ldots, \bar a_{\varphi(n)}\}.$$

*Proof.* $\gcd(a^i, n) = 1$ for all $i \ge 1$, so $\bar a^i \in \{\bar a_1, \ldots, \bar a_{\varphi(n)}\}$ for all $i \ge 1$. Since $\bar a, \bar a^2, \ldots, \bar a^{\varphi(n)}$ are incongruent, i.e. $\bar a^i \ne \bar a^j$ for $1 \le i < j \le \varphi(n)$,

$$
\begin{gathered}
\{\bar a, \bar a^2, \ldots, \bar a^{\varphi(n)}\} \subseteq \{\bar a_1, \ldots, \bar a_{\varphi(n)}\} \\
\Rightarrow\; \{\bar a, \bar a^2, \ldots, \bar a^{\varphi(n)}\} = \{\bar a_1, \ldots, \bar a_{\varphi(n)}\}. \quad \blacksquare
\end{gathered}
$$

**Corollary.** If $n$ has a primitive root, then the total number of primitive roots is $\varphi(\varphi(n))$.

!!! abstract "Theorem"
    If $p$ is a prime number and $d \mid p - 1$, then there are exactly $\varphi(d)$ incongruent integers having order $d$ modulo $p$.

*Proof.* Let $\psi(d)$ be the number of $k$ with $1 \le k \le p - 1$ such that $k$ has order $d$ modulo $p$. Then

$$p - 1 = \sum_{d \mid p-1} \psi(d),$$

and by Gauss,

$$p - 1 = \sum_{d \mid p-1} \varphi(d).$$

Therefore

$$\sum_{d \mid p-1} \psi(d) = \sum_{d \mid p-1} \varphi(d) \;\Rightarrow\; \sum_{d \mid p-1} \bigl[\varphi(d) - \psi(d)\bigr] = 0.$$

It is enough to show that

$$\varphi(d) \ge \psi(d) \quad \text{for all } d \mid p - 1. \tag{T}$$

- For $d \mid p - 1$, if $\psi(d) = 0$, then (T) is true.

- If $\psi(d) \ne 0$, there exists $a$ with $1 \le a \le p - 1$ such that the order of $a$ is $d$. Then $a$ is a solution to $x^d \equiv 1 \pmod p$, and clearly $a, a^2, a^3, \ldots, a^d$ are all distinct solutions to $x^d \equiv 1 \pmod p$.

- Therefore, by a corollary to Lagrange's theorem, $\{a, a^2, \ldots, a^d\}$ is the solution set of the equation $x^d \equiv 1 \pmod p$.

- Since $a$ has order $d$ mod $p$, $a^i$ has order $d$ mod $p$ iff $\gcd(i, d) = 1$. So in the set $\{a, a^2, \ldots, a^d\}$ there are exactly $\varphi(d)$ elements having order $d$, i.e. $\psi(d) = \varphi(d)$.

The claim is proved. $\blacksquare$

**Corollary.** If $p$ is a prime, then there are exactly $\varphi(p - 1)$ incongruent primitive roots of $p$.
