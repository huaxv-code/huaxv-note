# 最大公约数 gcd

!!! note "[872.最大公约数](https://www.acwing.com/problem/content/874/)"

    给定 $n$ 对正整数 $a_i, b_i$，请你求出每对数的最大公约数。

设 $d$ 是 $a、b$ 的公约数：

> - $d\ |\ a$，$d\ |\ b$
> - $d\ |\ (xa+yb)$

---

**证明 $d\ |\ (xa+yb)$**：

因为 $d\ |\ a$，$d\ |\ b$，所以设 $a = md,\ b = nd$，则 

> $(xa + yb) = (xmd + ynd) = d(xm + yn)$

所以 $d\ |\ (xa+yb)$

---

**证明 $d\ |\ (a\ \%\ b)$**：

1. 若 $a < b$ 则 $(a\ \%\ b) = a$，因为 $d\ |\ a$，$d\ |\ b$，所以 $d\ |\ (a\ \%\ b)$
2. 若 $a \geq b$ 则设 $k = a\ \%\ b$，所以 $a = xb + k$，所以 $k = xb - a$，由于 $d\ |\ (xb - a) = k$，所以 $d\ |\ (a\ \%\ b)$

综上：$d\ |\ (a\ \%\ b)$

---

**若 $a > b$，证明 $(a, b)$ 的公约数集合完全等同于 $(b, a\ \%\ b)$ 的公约数集合**

1. 设 $d$ 能整除 $a$ 和 $b$，设 $k = a\ \%\ b$，则 $k = a - xb$，所以 $d\ |\ k$，所以 $(a, b)$ 的公约数集合在 $(b, a\ \%\ b)$ 的公约数集合里面；
2. 设 $d$ 能整除 $b$ 和 $a\ \%\ b$，设 $k = a\ \%\ b$，则 $d\ |\ k$；且我们有：$a = xb + k$，而 $d\ |\ (xb + k = a)$，所以 $d\ |\ a$；所以 $(b, a\ \%\ b)$ 的公约数集合也在 $(a, b)$ 的公约数集合里面。

综上两点我们有：$(a, b)$ 的公约数集合完全等同于 $(b, a\ \%\ b)$ 的公约数集合

---

设计 `gcd` 代码：

```c++
typedef long long LL;

LL gcd(LL a, LL b)
{
    if (!a || !b) return a | b;
    return a > b ? gcd(b, a % b) : gcd(a, b % a);
}
```

---

??? note "[「872.最大公约数」代码参考](https://www.acwing.com/problem/content/874/)"

    给定 $n$ 对正整数 $a_i, b_i$，请你求出每对数的最大公约数。
    
    ```c++
    #include <bits/stdc++.h>

    using namespace std;
    int debuggersum = 0;

    // 即使是不成熟的尝试，

    typedef long long LL;

    LL gcd(LL a, LL b)
    {
        if (!a || !b) return a | b;
        return a > b ? gcd(b, a % b) : gcd(a, b % a);
    }

    void solve(void)
    {
        int n; scanf ("%d", &n);
        while (n --)
        {
            int a, b; scanf ("%d%d", &a, &b);
            printf ("%d\n", gcd(a, b));
        }
    }

    // 也胜于胎死腹中的策略。

    int main(void)
    {
        ifstream fi; ofstream fo;
        fi.open("./lrq.in"); fo.open("./lrq.out");
        if (fi.is_open() && fo.is_open())
        {
            fo << "start running ..." << endl; fo.close(); fi.close();
            for (long long i = 1; i <= 4e8 + 2e7; i++);
            FILE *fin = freopen("./lrq.in", "r", stdin);
            FILE *fout = freopen("./lrq.out", "w", stdout);
            solve(); fclose(fin); fclose(fout);
        }
        else solve();

        return 0;
    }
    ```