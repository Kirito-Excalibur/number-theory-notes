# Assignment 2 — Module II

MA502: Number Theory (Session: MO-2026), Department of Mathematics, BIT Mesra, Ranchi.

In these exercises lower case Latin letters $a, b, c, \ldots, x, y, z$ represent integers.

1. Let $a \equiv b \pmod m$ and $\alpha \equiv \beta \pmod m$. Show that

    1. $ax + \alpha y \equiv bx + \beta y \pmod m$ for all integers $x$ and $y$.

    2. $a\alpha \equiv b\beta \pmod m$.

    3. $a^n \equiv b^n \pmod m$ for every positive integer $n$.

    4. $f(a) \equiv f(b) \pmod m$ for every polynomial $f$ with integer coefficients.

2. Show that an integer $n > 0$ is divisible by 9 if and only if the sum of its digits in its decimal expansion is divisible by 9.

3. If $c > 0$, then show that $a \equiv b \pmod m$ if and only if $ac \equiv bc \pmod{mc}$.

4. **Cancellative law:** If $ac \equiv bc \pmod m$ and if $d = \gcd(m, c)$, then show that

    $$a \equiv b \pmod{\frac{m}{d}}.$$

    In other words, a common factor $c$ can be cancelled provided the modulus is divided by $d = (m, c)$. In particular, a common factor which is relatively prime to the modulus can always be cancelled.

5. Assume $a \equiv b \pmod m$. If $d \mid a$ and $d \mid m$, then show that $d \mid b$.

6. If $a \equiv b \pmod m$, then show that $\gcd(a, m) = \gcd(b, m)$.

7. If $a \equiv b \pmod m$ and if $0 \le |b - a| < m$, show that $a = b$.

8. Assume $a \equiv b \pmod m$ and $a \equiv b \pmod n$. If $\gcd(m, n) = 1$, show that $a \equiv b \pmod{mn}$.

9. Show that $a \equiv b \pmod m$ if and only if $a$ and $b$ give the same remainder when divided by $m$.

10. Assume $\gcd(k, m) = 1$, and $\bar a_1, \bar a_2, \bar a_3, \ldots, \bar a_m$ are integers. If $\mathbb{Z}_m = \{\bar a_1, \bar a_2, \bar a_3, \ldots, \bar a_m\}$, then show that $\mathbb{Z}_m = \{\overline{ka_1}, \overline{ka_2}, \overline{ka_3}, \ldots, \overline{ka_m}\}$.

11. Let $a = \sum_{i=1}^{100} i!$. Calculate $a \pmod{12}$.

12. Two parts:

    1. Find the remainders when $2^{50}$ and $41^{65}$ are divided by 7.

    2. What is the remainder when the following sum is divided by 4?

        $$1^5 + 2^5 + 3^5 + \cdots + 99^5 + 100^5.$$

13. Prove that the integer $53^{103} + 103^{53}$ is divisible by 39, and that $111^{333} + 333^{111}$ is divisible by 7.

14. For $n \ge 1$, use congruence theory to establish each of the following divisibility statements:

    1. $7 \mid 5^{2n} + 3 \cdot 2^{5n-2}$.

    2. $13 \mid 3^{n+2} + 4^{2n+1}$.

    3. $27 \mid 2^{5n+1} + 5^{n+2}$.

    4. $43 \mid 6^{n+2} + 7^{2n+1}$.

15. Prove the assertions below:

    1. If $a$ is an odd integer, then $a^2 \equiv 1 \pmod 8$.

    2. For any integer $a$, $a^3 \equiv 0, 1$, or $6 \pmod 7$.

    3. For any integer $a$, $a^4 \equiv 0$ or $1 \pmod 5$.

    4. If the integer $a$ is not divisible by 2 or 3, then $a^2 \equiv 1 \pmod{24}$.

16. If $p$ is a prime satisfying $n < p < 2n$, show that

    $$\binom{2n}{n} \equiv 0 \pmod p.$$

17. Solve the following linear congruences:

    1. $25x \equiv 15 \pmod{29}$.

    2. $5x \equiv 2 \pmod{26}$.

    3. $6x \equiv 15 \pmod{21}$.

    4. $36x \equiv 8 \pmod{102}$.

    5. $34x \equiv 60 \pmod{98}$.

    6. $140x \equiv 133 \pmod{301}$. *Hint: $\gcd(140, 301) = 7$.*

18. Solve each of the following sets of simultaneous congruences:

    1. $x \equiv 1 \pmod 3$, $x \equiv 2 \pmod 5$, $x \equiv 3 \pmod 7$.

    2. $x \equiv 5 \pmod{11}$, $x \equiv 14 \pmod{29}$, $x \equiv 15 \pmod{31}$.

    3. $x \equiv 5 \pmod 6$, $x \equiv 4 \pmod{11}$, $x \equiv 3 \pmod{17}$.

    4. $2x \equiv 1 \pmod 5$, $3x \equiv 9 \pmod 6$, $4x \equiv 1 \pmod 7$, $5x \equiv 9 \pmod{11}$.

19. If $p$ is a prime, and $f(x) = c_0 + c_1 x + \cdots + c_n x^n$ is a polynomial of degree $n$ with integer coefficients. If the congruence $f(x) \equiv 0 \pmod p$ has more than $n$ solutions, then show that every coefficient of $f$ is divisible by $p$.

20. Prove that $5n^3 + 7n^5 \equiv 0 \pmod{12}$ for all integers $n$.

21. Two parts:

    1. Find all positive integers $n$ for which $n^{13} \equiv n \pmod{1365}$.

    2. Find all positive integers $n$ for which $n^{17} \equiv n \pmod{4080}$.

22. Prove the converse of Wilson's theorem: If $(n - 1)! + 1 \equiv 0 \pmod n$, then $n$ is prime, provided $n > 1$.

23. Use Fermat's theorem to verify that 17 divides $11^{104} + 1$.

24. Three parts:

    1. If $\gcd(a, 35) = 1$, show that $a^{12} \equiv 1 \pmod{35}$. *Hint: From Fermat's theorem $a^6 \equiv 1 \pmod 7$ and $a^4 \equiv 1 \pmod 5$.*

    2. If $\gcd(a, 42) = 1$, show that $168 = 3 \cdot 7 \cdot 8$ divides $a^6 - 1$.

    3. If $\gcd(a, 133) = \gcd(b, 133) = 1$, show that $133 \mid a^{18} - b^{18}$.

25. From Fermat's theorem deduce that, for any integer $n \ge 0$, $13 \mid 11^{12n+6} + 1$.

26. Derive each of the following congruences:

    1. $a^{21} \equiv a \pmod{15}$ for all $a$. *Hint: By Fermat's theorem, $a^5 \equiv a \pmod 5$.*

    2. $a^7 \equiv a \pmod{42}$ for all $a$.

    3. $a^{13} \equiv a \pmod{3 \cdot 7 \cdot 13}$ for all $a$.

    4. $a^9 \equiv a \pmod{30}$ for all $a$.

27. If $\gcd(a, 30) = 1$, show that $60 \mid a^4 + 59$.

28. Two parts:

    1. Find the units digit of $3^{100}$ by the use of Fermat's theorem.

    2. For any integer $a$, verify that $a^5$ and $a$ have the same units digit.

29. If $7 \nmid a$, prove that either $a^3 + 1$ or $a^3 - 1$ is divisible by 7.

30. Two parts:

    1. Find the remainder when $15!$ is divided by 17.

    2. Find the remainder when $2(26!)$ is divided by 29.

31. Determine whether 17 is a prime by deciding whether $16! \equiv -1 \pmod{17}$.

32. Arrange the integers $2, 3, 4, \ldots, 21$ in pairs $a$ and $b$ that satisfy $ab \equiv 1 \pmod{23}$.

33. Show that $18! \equiv -1 \pmod{437}$.

34. Two parts:

    1. Prove that an integer $n > 1$ is prime if and only if $(n - 2)! \equiv 1 \pmod n$.

    2. If $n$ is a composite integer, show that $(n - 1)! \equiv 0 \pmod n$, except when $n = 4$.

35. Given a prime number $p$, establish the congruence

    $$(p - 1)! \equiv p - 1 \pmod{1 + 2 + 3 + \cdots + (p - 1)}.$$
