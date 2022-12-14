# 最小公倍数 lcm

由 $a \times b = gcd(a, b) \times lcm(a, b)$，得：

> $lcm(a, b) = a \times b \div gcd(a, b)$

---

**证明 $a \times b = gcd(a, b) \times lcm(a, b)$**:

令 $a = p_1^{k_1}p_2^{k_2} \cdots p_n^{k_n}$，$b = p_1^{s_1}p_2^{s_2} \cdots p_n^{s_n}$，则：

> $gcd(a, b) = p_1^{min(k_1, s_1)}p_2^{min(k_2, s_2)} \cdots p_n^{min(k_n, s_n)}$
> 
> $lcm(a, b) = p_1^{max(k_1, s_1)}p_2^{max(k_2, s_2)} \cdots p_n^{max(k_n, s_n)}$

所以：$a \times b = gcd(a, b) \times lcm(a, b)$

---

`lcm` 代码设计：

```c++
typedef long long LL;

LL gcd(LL a, LL b)
{
    if (!a || !b) return a | b;
    return a > b ? gcd(b, a % b) : gcd(a, b % a);
}

LL lcm(LL a, LL b)
{
    return a / gcd(a, b) * b;
}
```