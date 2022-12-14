# 数据结构的作用

可以用来训练自己的大脑

## oi 刷题配置

```c++
#include <bits/stdc++.h>

using namespace std;
int debuggersum = 0;

// 即使是不成熟的尝试，



void solve(void)
{
    
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

## sublime 代码片段配置

```c++ title="code.sublime-snippet"
<snippet>
	<content><![CDATA[
#include <bits/stdc++.h>

using namespace std;
int debuggersum = 0;

// 即使是不成熟的尝试，

${1}

void solve(void)
{
    
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
]]></content>
	<!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
	<!-- <tabTrigger>hello</tabTrigger> -->
	<!-- Optional: Set a scope to limit where the snippet will trigger -->
	<!-- <scope>source.python</scope> -->
	<tabTrigger>code</tabTrigger>
</snippet>
```