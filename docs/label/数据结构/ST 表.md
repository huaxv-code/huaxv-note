# ST 表

ST 表是用于解决 **可重复贡献问题** 的数据结构。

若满足 $f[x, x] = q[x]$，且若 $[x, y] = [x, a] \cup [b, y]$，则 $f[x, y] = f\{f[x, a], f[b, y]\}$，都可称为 **可重复贡献问题**。

例如下图的「区间最值」，就满足可重复贡献问题

![](../../img/ST%20表可重复贡献图.png)

同样道理：「区间 RMQ」、「区间 GCD」都是可重复贡献问题。RMQ 表示询问区间的最值。

类似「动态规划」的设计过程，初始化时，先确定长度为 1 的最值，再确定长度为 2 的最值，再确定长度为 4 的最值，两两合并依此类推，不断倍增预处理出各区间段的最值。

假设我要求区间 $[l, r]$ 的最值，我们要寻找 $[l, r]$ 的两个子区间：$[l, a]、[b, r]$ 使得 $[l, a] \cup [b, r] = [l, r]$，从而有：$f[l, r] = f\{f[l, a], f[b, r]\}$。

为了简化代码的设计，我们统一用区间的起点、区间的长度来代码该区间：$f(l, len)$ 代表区间 $[l, l + 2 ^ {len} - 1]$ 的最值。

则区间 $[l, r]$ 的最值为：$f\{f(l, log(r - l + 1)), f(r - 2 ^ {log(r - l + 1)} + 1, log(r - l + 1))\}$

!!! note "[P3865 【模板】ST 表](https://www.luogu.com.cn/problem/P3865)"

    给定一个长度为 $N$ 的数列，和 $M$ 次询问，求出每一次「询问的区间」内「数字最大的值」。

## read 快读

借助 `getchar` 加快数据的读取速度。

```c++
inline int read()
{
    int x = 0, f = 1; char c = getchar();
    while (c < '0' || c > '9') { if (c == '-') f = -1; c = getchar(); }
    while (c >= '0' && c <= '9') { x = x * 10 + c - '0'; c = getchar(); }
    return x * f;
}
```

## init 初始化 ST 表

使用类似动态规划的代码实现方式，先枚举每一个区间长度为 1 的，再枚举每一个区间长度为 2 的，接着枚举每一个区间长度为 4 的，依此类推：

??? note "ST 表树"
    ![ST%20表树](../../img/ST%20表树.png){width=100%}

    该树的每一个节点都会是以该节点为树根的子树的叶子节点的最大值。

    例如右图蓝色部分的子树，该子树的根节点是 $6$，管理的叶子节点有 $[4, 6, 1]$，则 $6$ 就是管理该集合 $[4, 6, 1]$ 的最大值。

```c++
const int N = int (1e6 + 10);
int n, m;
int a[N], f[N][25], lg2[N]; 
// a 代表数据数组
// f[l][len] 代表区间 [l, l + 1 << len - 1] 的最大值
// lg2[i] 代表 log(i) 的值

void init()
{
    for (int i = 1; i <= n; i ++) f[i][0] = a[i];
    for (int i = 1; (1 << i) <= n; i ++)
        for (int j = 1; j + (1 << i) - 1 <= n; j ++)
            f[j][i] = max(f[j][i - 1], f[j + (1 << (i - 1))][i - 1]);
}
```

## prelg2 预先处理出 log2 数组

|`x`|`lg2[x]`|`x`|`lg2[x]`|
|:--:|:--:|:--: |:--:|
| 1 | 0 | 9 | 3 |
| 2 | 1 | 10 | 3 |
| 3 | 1 | 11 | 3 |
| 4 | 2 | 12 | 3 |
| 5 | 2 | 13 | 3 |
| 6 | 2 | 14 | 3 |
| 7 | 2 | 15 | 3 |
| 8 | 3 | 16 | 4 |

由递推关系有：

```c++
x == 1, lg2[1] = 0

x >= 2, lg2[x] = lg2[x / 2] + 1
```

代码实现：

```c++
void prelg2(int n)
{
    lg2[1] = 0;
    for (int i = 2; i <= n; i ++) lg2[i] = lg2[i / 2] + 1;
}
```

## getmax 获取区间 [l, r] 的最大值

```c++
int getmax(int l, int r)
{
    int len = lg2[r - l + 1]; // 获取合适的子区间长度
    return max(f[l][len], f[r - (1 << len) + 1][len]);
}
```

??? note "[P3865 【模板】ST 表 代码参考](https://www.luogu.com.cn/problem/P3865)"

    ```c++
    // 即使是不成熟的尝试，

    inline int read()
    {
        int x = 0, f = 1; char c = getchar();
        while (c < '0' || c > '9') { if (c == '-') f = -1; c = getchar(); }
        while (c >= '0' && c <= '9') { x = x * 10 + c - '0'; c = getchar(); }
        return x * f;
    }

    const int N = int (1e6 + 10);
    int n, m;
    int a[N], f[N][25], lg2[N]; 
    // a 代表数据数组
    // f[l][len] 代表区间 [l, l + 1 << len - 1] 的最大值
    // lg2[i] 代表 log(i) 的值

    void prelg2(int n)
    {
        lg2[1] = 0;
        for (int i = 2; i <= n; i ++) lg2[i] = lg2[i / 2] + 1;
    }

    void init()
    {
        for (int i = 1; i <= n; i ++) f[i][0] = a[i];
        for (int i = 1; (1 << i) <= n; i ++)
            for (int j = 1; j + (1 << i) - 1 <= n; j ++)
                f[j][i] = max(f[j][i - 1], f[j + (1 << (i - 1))][i - 1]);
    }

    int getmax(int l, int r)
    {
        int len = lg2[r - l + 1]; // 获取合适的子区间长度
        return max(f[l][len], f[r - (1 << len) + 1][len]);
    }

    void solve(void)
    {
        n = read(); m = read();
        for (int i = 1; i <= n; i ++) a[i] = read();
        prelg2(n); init();
        while (m --)
        {
            int l, r; l = read(); r = read();
            printf ("%d\n", getmax(l, r));
        }
    }

    // 也胜于胎死腹中的策略。
    ```