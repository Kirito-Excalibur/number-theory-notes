# Assignment 1 — Module I

MA502: Number Theory (Session: MO-2026), Department of Mathematics, BIT Mesra, Ranchi.

In these exercises lower case Latin letters $a, b, c, \ldots, x, y, z$ represent integers.

1. If $\gcd(a, b) = 1$ and if $c \mid a$ and $d \mid b$, then $\gcd(c, d) = 1$.

2. If $\gcd(a, b) = \gcd(a, c) = 1$, then $\gcd(a, bc) = 1$.

3. If $\gcd(a, b) = 1$, then $\gcd(a^n, b^k) = 1$ for all $n \ge 1$, $k \ge 1$.

4. If $\gcd(a, b) = 1$, then $\gcd(a + b, a - b)$ is either 1 or 2.

5. If $\gcd(a, b) = 1$, then

    $$\gcd(a + b,\ a^2 - ab + b^2)$$

    is either 1 or 3.

6. If $\gcd(a, b) = 1$ and if $d \mid (a + b)$, then

    $$\gcd(a, d) = \gcd(b, d) = 1.$$

7. Prove that if $d$ is a common divisor of $a$ and $b$, then

    $$\gcd(a, b) = d \quad\text{if and only if}\quad \gcd(a/d,\ b/d) = 1.$$

8. A rational number $a/b$ with $\gcd(a, b) = 1$ is called a *reduced fraction*. If the sum of two reduced fractions is an integer, say

    $$\frac{a}{b} + \frac{c}{d} = n,$$

    prove that $|b| = |d|$.

9. An integer is called *squarefree* if it is not divisible by the square of any prime. Prove that for every $n \ge 1$ there exist uniquely determined $a > 0$ and $b > 0$ such that

    $$n = a^2 b,$$

    where $b$ is squarefree.

10. For each of the following statements, either give a proof or exhibit a counterexample.

    1. If $b^2 \mid n$ and $a^2 \mid n$ and $a^2 \le b^2$, then $a \mid b$.

    2. If $b^2$ is the largest square divisor of $n$, then $a^2 \mid n$ implies $a \mid b$.

11. Given $x$ and $y$, let

    $$m = ax + by, \qquad n = cx + dy,$$

    where $ad - bc = \pm 1$. Prove that $\gcd(m, n) = \gcd(x, y)$.

12. Use the Euclidean Algorithm to obtain integers $x$ and $y$ satisfying the following:

    1. $\gcd(56, 72) = 56x + 72y$.

    2. $\gcd(24, 138) = 24x + 138y$.

    3. $\gcd(119, 272) = 119x + 272y$.

    4. $\gcd(1769, 2378) = 1769x + 2378y$.

13. Prove that $n^4 + 4$ is composite if $n > 1$.

14. For each of the following statements either give a proof or exhibit a counterexample.

    1. If $a^n \mid b^n$, then $a \mid b$.

    2. If $n^n \mid m^m$, then $n \mid m$.

    3. If $a^n \mid 2b^n$ and $n > 1$, then $a \mid b$.

15. Two parts:

    1. If $\gcd(a, b) = 1$ and $\left(\frac{a}{b}\right)^m = n$, prove that $b = 1$.

    2. If $n$ is not the $m$th power of a positive integer, prove that $n^{1/m}$ is irrational.

16. If $\gcd(a, b) = 1$ and $ab = c^n$, prove that

    $$a = x^n \quad\text{and}\quad b = y^n$$

    for some $x$ and $y$. *Hint: Consider $d = \gcd(a, c)$.*

17. Prove that every $n \ge 12$ is the sum of two composite numbers.

18. Prove that if $2^n - 1$ is prime, then $n$ is prime.

19. Prove that if $2^n + 1$ is prime, then $n$ is a power of 2.

20. Use the Division Algorithm to establish the following:

    1. The square of any integer is either of the form $3k$ or $3k + 1$.

    2. The cube of any integer has one of the forms $9k$, $9k + 1$, or $9k + 8$.

    3. The fourth power of any integer is either of the form $5k$ or $5k + 1$.

21. Prove that $3a^2 - 1$ is never a perfect square.

22. For $n \ge 1$, prove that

    $$\frac{n(n + 1)(2n + 1)}{6}$$

    is an integer. *Hint: By the Division Algorithm, $n$ has one of the forms $6k, 6k + 1, \ldots, 6k + 5$; establish the result in each of these six cases.*

23. Which of the following Diophantine equations cannot be solved?

    1. $6x + 51y = 22$.

    2. $33x + 14y = 115$.

    3. $14x + 35y = 93$.

24. Determine all solutions in the integers of the following Diophantine equations:

    1. $56x + 72y = 40$.

    2. $24x + 138y = 18$.

    3. $221x + 35y = 11$.

25. Determine all solutions in the positive integers of the following Diophantine equations:

    1. $18x + 5y = 48$.

    2. $54x + 21y = 906$.

    3. $123x + 360y = 99$.

    4. $158x - 57y = 7$.

26. Find all integers $n$ such that

    1. $\varphi(n) = \dfrac{n}{2}$.

    2. $\varphi(n) = \varphi(2n)$.

    3. $\varphi(n) = 12$.

27. For each of the following statements either give a proof or exhibit a counterexample.

    1. If $\gcd(m, n) = 1$, then $\gcd(\varphi(m), \varphi(n)) = 1$.

    2. If $n$ is composite, then $\gcd(n, \varphi(n)) > 1$.

    3. If the same primes divide $m$ and $n$, then $n\varphi(m) = m\varphi(n)$.

28. Prove that

    $$\frac{n}{\varphi(n)} = \sum_{d \mid n} \frac{\mu^2(d)}{\varphi(d)}.$$
