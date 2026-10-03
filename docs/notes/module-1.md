# Module 1 — Divisibility & Arithmetic Functions

## Divisibility

**Motivation.** Find the integer solutions of the equation

$$ax + by = c, \qquad a, b, c \in \mathbb{Z}.$$

We finally show that the equation has an integer solution if and only if $\gcd(a, b)$ divides $c$.

## Well-Ordering Principle

**Motivation.** Suppose some positive integers are marked on the number line. Could there be marked numbers but no first marked number? The answer is no (why?).

Consider the statement $n! \le 2^n$ for $n \ge 1$. Clearly the statement is false for $n = 6$. Is there always a smallest number for which the statement is not true?

!!! abstract "Well-Ordering Principle"
    Every non-empty subset $S$ of positive integers has a least element; i.e., there is an integer $a \in S$ such that $a \le b$ for all $b \in S$.

## Mathematical Induction

**Motivation.**

- *Passing a message along a line.* Suppose infinitely many people sit in a line, and you know (i) the first person receives the message, and (ii) when a person receives the message, they immediately pass it to the person next to them. Then everyone eventually receives the message.

- *Domino effect.* Imagine infinitely many dominoes arranged in a line. (i) Push the first domino; (ii) every domino knocks down the next one. Then every domino falls.

!!! abstract "Theorem (Mathematical Induction)"
    Let $P(n)$ be a statement such that

    1. $P(1)$ is true, and

    2. $P(k)$ true $\Rightarrow$ $P(k+1)$ true, for all $k \ge 1$.

    Then $P(n)$ is true for all $n \in \mathbb{N}$.

**Exercise.** Using induction, show that for all $n \ge 1$:

1. $n! = (n-1)! \cdot n$

2. $1 + 2 + 3 + \cdots + n = \dfrac{n(n+1)}{2}$

3. $1^2 + 2^2 + \cdots + n^2 = \dfrac{n(2n+1)(n+1)}{6}$

4. Given real numbers $a, b$: $\displaystyle (a+b)^n = \sum_{i=0}^{n} \binom{n}{i} a^i b^{n-i}$

## Division Algorithm

!!! abstract "Theorem"
    Given integers $a$ and $b$ with $b > 0$, there exist unique integers $q$ and $r$ such that

    $$a = bq + r, \qquad 0 \le r < b.$$

    $q$ is called the *quotient* and $r$ the *remainder*.

**Application.** Show that for any integer $a$, $\dfrac{a(a^2+2)}{3}$ is an integer.

*Solution.* Any integer $a$ has one of the forms $3k$, $3k+1$, $3k+2$.

- If $a = 3k$, then $\frac{a(a^2+2)}{3} = k(9k^2 + 2) \in \mathbb{Z}$.

- If $a = 3k+1$, then $\frac{a(a^2+2)}{3} = (3k+1)(3k^2 + 2k + 1) \in \mathbb{Z}$.

- If $a = 3k+2$, then $\frac{a(a^2+2)}{3} = (3k+2)(3k^2 + 4k + 2) \in \mathbb{Z}$.

## Greatest Common Divisor (GCD)

**Definition.** Let $a, b \in \mathbb{Z}$. Then $d = \gcd(a, b)$ if

1. $d \mid a$ and $d \mid b$, and

2. if $c$ divides both $a$ and $b$, then $c \le d$.

!!! abstract "Lemma"
    $d = \gcd(a, b) \iff$ (if $c \mid a$ and $c \mid b$, then $c \mid d$).

*Sketch.* $(\Leftarrow)$ is okay. $(\Rightarrow)$ By the division algorithm, $d = cq + r$, $0 \le r < c$. Assume $r > 0$. Write $a = dx$, $b = dy$ and $a = cz$, $b = cw$.

- Observe that $\gcd(x, y) = 1$: if $d' = \gcd(x, y)$, then $dd'$ is a common divisor of $a$ and $b$, so $dd' \le d \Rightarrow d' \le 1 \Rightarrow d' = 1$ (since $d' > 0$).

- Now $a = dx = (cq + r)x \Rightarrow c(z - xq) = rx \Rightarrow c \mid rx$. Similarly $c \mid ry$.

- Hence $c \le \gcd(rx, ry) = r\gcd(x, y) = r$, a contradiction since $r < c$. $\blacksquare$

!!! abstract "Theorem (Bézout)"
    Given integers $a$ and $b$, not both zero, there exist integers $p$ and $q$ such that

    $$\gcd(a, b) = ap + bq.$$

*Proof.* Consider the set

$$S = \{au + bv \mid u, v \in \mathbb{Z} \text{ and } au + bv > 0\}.$$

- If $a \ne 0$, then $|a| = a \cdot u + b \cdot 0$ for $u = +1$ or $-1$, i.e. $|a| \in S$, so $S \ne \emptyset$.

- By the well-ordering principle, $S$ has a smallest element $d$. Then $d > 0$ and $d = ap + bq$ for some $p, q \in \mathbb{Z}$.

- *Claim:* $d = \gcd(a, b)$. Write $a = dq' + r$, $0 \le r < d$. Then $r = a - dq' = a(1 - pq') - b(qq')$. If $r > 0$ then $r \in S$, so $d \le r$, a contradiction; hence $r = 0$, i.e. $d \mid a$. Similarly $d \mid b$.

- Now let $c \mid a$ and $c \mid b \Rightarrow a = cs$, $b = ct$. Then $d = ap + bq = c(sp + tq) \Rightarrow c \le d$.

Hence $d = \gcd(a, b)$ by definition. $\blacksquare$

**Definition.** Two integers $a, b$ are said to be *relatively prime* if $\gcd(a, b) = 1$.

!!! abstract "Theorem"
    Let $a, b \in \mathbb{Z}$, not both zero. Then $a$ and $b$ are relatively prime $\iff$ there exist integers $p, q$ such that $ap + bq = 1$.

*Proof.* $(\Rightarrow)$ is immediate by the above theorem. $(\Leftarrow)$ Let $d = \gcd(a, b)$, so $a = du$ and $b = dv$. Then $ap + bq = 1 \Rightarrow d(up + vq) = 1 \Rightarrow d = 1$ (since $d > 0$). $\blacksquare$

- **Corollary 1.** $\gcd(a, b) = d \Rightarrow \gcd\left(\frac{a}{d}, \frac{b}{d}\right) = 1$.

- **Corollary 2.** $a \mid c$, $b \mid c$ with $\gcd(a, b) = 1 \Rightarrow ab \mid c$.

- **Corollary 3.** If $a \mid bc$ with $\gcd(a, b) = 1$, then $a \mid c$.

## Algorithm to find $x$ and $y$ such that $\gcd(a, b) = ax + by$

!!! abstract "Lemma"
    If $a = bq + r$, then $\gcd(a, b) = \gcd(b, r)$.

*Proof.* Let $d = \gcd(a, b)$. Then $d \mid a$, $d \mid b \Rightarrow d \mid a - bq \Rightarrow d \mid r$. If $c \mid b$ and $c \mid r$, then $c \mid a$, so $c \le d$ (since $d = \gcd(a, b)$). By definition, $d = \gcd(b, r)$. $\blacksquare$

**Euclidean Algorithm.** Our objective is to find $x$ and $y$ such that $ax + by = \gcd(a, b)$. Without loss of generality assume $a > b$ and $b \nmid a$.

| Step | Range | Consequence |
| --- | --- | --- |
| $a = bq_1 + r_1$ | $0 < r_1 < b$ | $\gcd(a, b) = \gcd(b, r_1)$ |
| $b = r_1 q_2 + r_2$ | $0 < r_2 < r_1$ | $\gcd(b, r_1) = \gcd(r_1, r_2)$ |
| $r_1 = r_2 q_3 + r_3$ | $0 < r_3 < r_2$ | $\gcd(r_1, r_2) = \gcd(r_2, r_3)$ |
| $\vdots$ | $\vdots$ | $\vdots$ |
| $r_{n-2} = q_n r_{n-1} + r_n$ | $0 < r_n < r_{n-1}$ | $\gcd(r_{n-2}, r_{n-1}) = \gcd(r_{n-1}, r_n)$ |
| $r_{n-1} = q_{n+1} r_n + 0$ | | $\gcd(r_{n-1}, r_n) = r_n$ |

**Example 1.** $12x + 30y = 6$, with $\gcd(12, 30) = 6$.

$$30 = 2 \cdot 12 + 6, \quad 12 = 2 \cdot 6 + 0 \;\Rightarrow\; 6 = 12 \cdot (-2) + 30 \cdot 1,$$

i.e. $x = -2$, $y = 1$.

**Example 2.** $17x + 7y = 1$.

$$17 = 2 \cdot 7 + 3, \quad 7 = 2 \cdot 3 + 1, \quad 3 = 3 \cdot 1.$$

$$1 = 7 - 2 \cdot 3 = 7 - 2(17 - 2 \cdot 7) = (-2) \cdot 17 + 5 \cdot 7,$$

so $x = -2$, $y = 5$.

**Example 3.** $35x + 22y = 1$, with $\gcd(35, 22) = 1$.

$$35 = 1 \cdot 22 + 13, \quad 22 = 1 \cdot 13 + 9, \quad 13 = 1 \cdot 9 + 4, \quad 9 = 2 \cdot 4 + 1, \quad 4 = 4 \cdot 1 + 0.$$

$$
\begin{aligned}
1 &= 9 - 2 \cdot 4 = 9 - 2(13 - 1 \cdot 9) = 3 \cdot 9 - 2 \cdot 13 \\
  &= 3(22 - 1 \cdot 13) - 2 \cdot 13 = 3 \cdot 22 - 5 \cdot 13 \\
  &= 3 \cdot 22 - 5(1 \cdot 35 - 1 \cdot 22) = (-5) \cdot 35 + 8 \cdot 22,
\end{aligned}
$$

so $x = -5$, $y = 8$.

## Linear Diophantine Equation

An equation of the form $ax + by = c$, with $a, b, c \in \mathbb{Z}$, is called a *linear Diophantine equation*.

!!! abstract "Divisibility Theorem"
    The linear Diophantine equation $ax + by = c$ has a solution if and only if $\gcd(a, b) \mid c$. If $(x_0, y_0)$ is any particular solution of $ax + by = c$, then all the other solutions are given by (with $d = \gcd(a, b)$)

    $$x = x_0 + \frac{b}{d} t, \qquad y = y_0 - \frac{a}{d} t, \qquad t \in \mathbb{Z}.$$

**Corollary.** If $\gcd(a, b) = 1$, then $ax + by = c$ has an integer solution. If $(x_0, y_0)$ is a particular solution, then all solutions are given by $x = x_0 + bt$, $y = y_0 - at$, $t \in \mathbb{Z}$.

**Examples.**

1. The equation $12x + 30y = 18$ has a particular solution $x_0 = -6$, $y_0 = 3$. All the solutions are given by $x = -6 + 5t$, $y = 3 - 2t$.

2. The equation $12x + 30y = 15$ has no solution.

## Fundamental Theorem of Arithmetic

**Definition.** An integer $p > 1$ is called a *prime number* if its only positive divisors are 1 and $p$. If it is not prime, it is called *composite*.

!!! abstract "Lemma (Euclid)"
    Let $p$ be a prime number and $p \mid ab$. Then either $p \mid a$ or $p \mid b$.

*Proof.* Assume $p \nmid a \Rightarrow \gcd(p, a) = 1$. Then $p \mid ab \Rightarrow p \mid b$. $\blacksquare$

- **Corollary 1.** If $p$ is a prime and $p \mid a_1 \cdots a_n$, then $p \mid a_k$ for some $1 \le k \le n$.

- **Corollary 2.** If $p, a_1, \ldots, a_n$ are all prime, then $p \mid a_1 \cdots a_n \Rightarrow p = a_k$ for some $1 \le k \le n$.

!!! abstract "Theorem (Fundamental Theorem of Arithmetic)"
    Every positive integer $n > 1$ is either a prime or a product of primes; this representation is unique, apart from the order in which the factors occur. That is,

    $$n = p_1^{\alpha_1} \cdots p_r^{\alpha_r},$$

    where $p_1, \ldots, p_r$ are primes and $\alpha_1, \ldots, \alpha_r \in \mathbb{N}$.

**Exercise.** Let $m = p_1^{\alpha_1} \cdots p_r^{\alpha_r}$ and $n = p_1^{\beta_1} \cdots p_r^{\beta_r}$. Show that

$$\gcd(m, n) = \prod_{i=1}^{r} p_i^{\min\{\alpha_i, \beta_i\}} \quad\text{and}\quad \operatorname{lcm}(m, n) = \prod_{i=1}^{r} p_i^{\max\{\alpha_i, \beta_i\}}.$$

!!! abstract "Theorem (Euclid)"
    There are infinitely many primes.

*Proof.* If not, let $S = \{p_1, \ldots, p_n\}$ be the set of all prime numbers. Consider $a = (p_1 \cdots p_n) + 1$. Then none of the $p_i$ divide $a$, so there is at least one prime number which does not belong to $S$, a contradiction. $\blacksquare$

## Arithmetic Functions

### Euler's $\varphi$ function

**Definition.** Let $n \ge 1$. Define $\varphi(n)$ to be the number of positive integers $m \le n$ such that $\gcd(m, n) = 1$.

$$\varphi(1) = 1,\ \varphi(2) = 1,\ \varphi(3) = 2,\ \varphi(4) = 2,\ \varphi(5) = 4,\ \varphi(6) = 2.$$

!!! abstract "Lemma"
    If $m$ and $n$ are relatively prime, then $\varphi(mn) = \varphi(m)\varphi(n)$.

*Proof.* $\varphi(mn) = \bigl|\{k \in \mathbb{Z} : 1 \le k \le mn,\ \gcd(k, mn) = 1\}\bigr|$. Note that $\gcd(k, mn) = 1 \iff \gcd(k, m) = 1$ and $\gcd(k, n) = 1$. Arrange the numbers as an $m \times n$ array:

$$
\begin{array}{ccccc}
1 & 2 & 3 & \cdots & n \\
n+1 & n+2 & n+3 & \cdots & 2n \\
\vdots & \vdots & \vdots & & \vdots \\
(m-1)n+1 & (m-1)n+2 & (m-1)n+3 & \cdots & mn
\end{array}
$$

- The $k$th row's elements are of the form $kn + r$, and $\gcd(kn + r, n) = \gcd(r, n)$. So there are $\varphi(n)$ columns of the array such that $\gcd(kn + r, n) = 1$ for all $0 \le k \le m - 1$.

- Fix one such column, i.e. fix $r$ such that $\gcd(r, n) = 1$. We check how many elements in this column are coprime to $m$ as well.

- For two different elements $k_1 n + r$ and $k_2 n + r$, write $k_1 n + r = mq_1 + r_1$ and $k_2 n + r = mq_2 + r_2$. If $r_1 = r_2$, then $m \mid (k_1 - k_2)n \Rightarrow m \mid k_1 - k_2$ (since $\gcd(m, n) = 1$) $\Rightarrow k_1 = k_2$.

- Therefore, upon division by $m$, the elements $r, n + r, \ldots, (m-1)n + r$ produce different remainders. If $kn + r = mq + r_1$, then $\gcd(kn + r, m) = \gcd(r_1, m)$.

- So the number of elements in the $r$th column which are coprime to $m$ is $\varphi(m)$, and in total there are $\varphi(m)\varphi(n)$ integers coprime to both $m$ and $n$ ($\iff$ coprime to $mn$).

That is, $\varphi(mn) = \varphi(m)\varphi(n)$. $\blacksquare$

!!! abstract "Lemma"
    If $p$ is prime, then $\varphi(p^\alpha) = p^\alpha - p^{\alpha - 1}$.

*Proof.* $\gcd(k, p^\alpha) \ne 1 \iff p \mid k \iff k = pt$ for some $1 \le t \le p^{\alpha-1}$. Therefore $\varphi(p^\alpha) = p^\alpha - p^{\alpha-1}$. $\blacksquare$

!!! abstract "Theorem"
    If $n \ge 1$, then

    $$\varphi(n) = n \prod_{\substack{p \mid n \\ p \text{ prime}}} \left(1 - \frac{1}{p}\right).$$

*Proof.* Write $n = p_1^{\alpha_1} \cdots p_r^{\alpha_r}$. Then

$$
\begin{aligned}
\varphi(n) &= \varphi(p_1^{\alpha_1}) \cdots \varphi(p_r^{\alpha_r}) = (p_1^{\alpha_1} - p_1^{\alpha_1 - 1}) \cdots (p_r^{\alpha_r} - p_r^{\alpha_r - 1}) \\
&= p_1^{\alpha_1}\left(1 - \tfrac{1}{p_1}\right) \cdots p_r^{\alpha_r}\left(1 - \tfrac{1}{p_r}\right) = n\left(1 - \tfrac{1}{p_1}\right)\left(1 - \tfrac{1}{p_2}\right) \cdots \left(1 - \tfrac{1}{p_r}\right). \qquad \blacksquare
\end{aligned}
$$

!!! abstract "Lemma"

    1. If $d = \gcd(m, n)$, then $\varphi(mn) = \varphi(m)\varphi(n)\left(\dfrac{d}{\varphi(d)}\right)$.

    2. $a \mid b \Rightarrow \varphi(a) \mid \varphi(b)$.

    3. If $n \ge 3$, $\varphi(n)$ is even.

!!! abstract "Theorem (Gauss)"
    If $n \ge 1$, we have $\displaystyle n = \sum_{d \mid n} \varphi(d)$.

*Proof.* Let $S = \{1, 2, \ldots, n\}$. For each $d \mid n$, let $A(d) = \{k \in S : \gcd(k, n) = d\}$. Then

$$S = \bigsqcup_{d \mid n} A(d) \;\Rightarrow\; n = \sum_{d \mid n} |A(d)|.$$

Now $\gcd(k, n) = d \iff \gcd\left(\frac{k}{d}, \frac{n}{d}\right) = 1 \Rightarrow |A(d)| = \varphi\left(\frac{n}{d}\right)$. So

$$n = \sum_{d \mid n} \varphi\left(\frac{n}{d}\right) = \sum_{d \mid n} \varphi(d). \qquad \blacksquare$$

### The Möbius function

$$
\mu(1) = 1; \qquad \text{for } n > 1,\ n = p_1^{\alpha_1} \cdots p_k^{\alpha_k}: \quad
\mu(n) = \begin{cases} (-1)^k & \text{if } \alpha_1 = \alpha_2 = \cdots = \alpha_k = 1, \\ 0 & \text{otherwise.} \end{cases}
$$

| $n$ | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| $\mu(n)$ | 1 | −1 | −1 | 0 | −1 | 1 | −1 |

!!! abstract "Theorem"
    If $n \ge 1$,

    $$\sum_{d \mid n} \mu(d) = \begin{cases} 1 & \text{if } n = 1, \\ 0 & \text{if } n > 1. \end{cases}$$

*Proof.* For $n > 1$, write $n = p_1^{\alpha_1} \cdots p_k^{\alpha_k}$. Then

$$
\begin{aligned}
\sum_{d \mid n} \mu(d) &= \mu(1) + \mu(p_1) + \cdots + \mu(p_k) + \mu(p_1 p_2) + \cdots + \mu(p_{k-1} p_k) + \cdots + \mu(p_1 \cdots p_k) \\
&= 1 + \binom{k}{1}(-1) + \binom{k}{2}(1) + \cdots + \binom{k}{k}(-1)^k = (1 - 1)^k = 0. \qquad \blacksquare
\end{aligned}
$$

!!! abstract "Möbius inversion formula"
    If $n \ge 1$, then $\displaystyle \varphi(n) = \sum_{d \mid n} \mu(d) \frac{n}{d}$.

*Proof.*

$$
\begin{aligned}
\varphi(n) &= \sum_{k=1}^{n} \left\lfloor \frac{1}{\gcd(k, n)} \right\rfloor = \sum_{k=1}^{n} \sum_{d \mid \gcd(k, n)} \mu(d) = \sum_{k=1}^{n} \sum_{\substack{d \mid k \\ d \mid n}} \mu(d) \\
&= \sum_{d \mid n} \sum_{\substack{1 \le k \le n \\ d \mid k}} \mu(d) = \sum_{d \mid n} \mu(d) \, \bigl|\{k : 1 \le k \le n,\ d \mid k\}\bigr| = \sum_{d \mid n} \mu(d) \frac{n}{d}. \qquad \blacksquare
\end{aligned}
$$

!!! abstract "General Möbius inversion formula"
    Let $f, g$ be two arithmetical functions. Then

    $$f(n) = \sum_{d \mid n} g(d) \iff g(n) = \sum_{d \mid n} f(d) \, \mu\!\left(\frac{n}{d}\right).$$

### Other number-theoretic functions: $\sigma(n)$ and $\tau(n)$

$$\tau(n) = \sum_{d \mid n} 1 = \text{number of positive divisors of } n, \qquad \sigma(n) = \sum_{d \mid n} d = \text{sum of all positive divisors of } n.$$

!!! abstract "Proposition"
    If $n = p_1^{\alpha_1} \cdots p_r^{\alpha_r}$, then

    $$\tau(n) = (\alpha_1 + 1)(\alpha_2 + 1) \cdots (\alpha_r + 1), \qquad \sigma(n) = \frac{p_1^{\alpha_1+1} - 1}{p_1 - 1} \cdot \frac{p_2^{\alpha_2+1} - 1}{p_2 - 1} \cdots \frac{p_r^{\alpha_r+1} - 1}{p_r - 1}.$$

    In particular, both $\sigma$ and $\tau$ are multiplicative.
