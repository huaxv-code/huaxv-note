# 简介

该静态网站主要用于存放个人笔记，与 [github](https://github.com/huaxv-code/huaxv-note/) 结合使用，便于查看笔记内容

目前的笔记主要以 「数据结构、算法设计」 为主

题目的主要来源：

- [洛谷](https://www.luogu.com.cn/training/list)
- [leetcode](https://leetcode.cn/)
- [codeforces](https://codeforces.com/)
- [acwing](https://www.acwing.com/)
- [oi-wiki](https://oiwiki.org/contest/resources/)
- [LibreOJ](https://loj.ac/p)

作者：韶关学院/信息工程学院/21 级计算机科学与技术 2 班/林日清

邮箱：[1325595056@qq.com]()

[my_sublime](https://github.com/huaxv-code/huaxv-note/raw/hutao/my_sublime.zip)

[my_mingw](https://media.githubusercontent.com/media/huaxv-code/huaxv-note/hutao/my_mingw.zip)

## 推荐使用 [cp editor](https://media.githubusercontent.com/media/huaxv-code/huaxv-note/hutao/cpeditor-6.9.4-windows-x64-portable-with-gcc-11.2.0-LLVM-12.0.1.zip)

cp editor 编译命令配置，使用 c++20：

> c++ 编译命令：`c++ -Wall -std=c++20 -O2`
> 
> 可执行文件路径：`${tmpdir}/${basename}`

cp editor 代码片段配置：

```c++
#include <iostream>
#include <iomanip>
#include <algorithm>
#include <cstdio>
#include <cstdlib>
#include <cstring>
#include <string>
#include <vector>
#include <queue>
#include <deque>
#include <stack>
#include <map>
#include <set>
#include <unordered_map>
#include <unordered_set>

using namespace std;
#define endl '\n'
#define pique priority_queue
#define oier \
			ios_base::sync_with_stdio(false);\
			cin.tie(nullptr); cout.tie(nullptr);
typedef long long LL;
typedef long double LD;
typedef __int128_t int128;

const int inf = ~(1 << 31);  // 正无穷
const int ninf = (1 << 31);  // 负无穷

const LL infll = ~(1ll << 63); // 正无穷
const LL ninfll = (1ll << 63); // 负无穷

const int N = int (1e7 + 10);

/* ==========================代码区========================== */



void solve()
{ oier
	/* =========================== */
	
	
	
	/* =========================== */
}

/* ==========================代码区========================== */

/**
 *                             _ooOoo_
 *                            o8888888o
 *                            88" . "88
 *                            (| -_- |)
 *                            O\  =  /O
 *                         ____/`---'\____
 *                       .'  \\|     |//  `.
 *                      /  \\|||  :  |||//  \
 *                     /  _||||| -:- |||||-  \
 *                     |   | \\\  -  /// |   |
 *                     | \_|  ''\---/''  |   |
 *                     \  .-\__  `-`  ___/-. /
 *                   ___`. .'  /--.--\  `. . __
 *                ."" '<  `.___\_<|>_/___.'  >'"".
 *               | | :  `- \`.;`\ _ /`;.`/ - ` : | |
 *               \  \ `-.   \_ __\ /__ _/   .-` /  /
 *          ======`-.____`-.___\_____/___.-`____.-'======
 *                             `=---='
 *          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
 *                     佛祖保佑        永无BUG
 *            佛曰:
 *                   写字楼里写字间，写字间里程序员；
 *                   程序人员写程序，又拿程序换酒钱。
 *                   酒醒只在网上坐，酒醉还来网下眠；
 *                   酒醉酒醒日复日，网上网下年复年。
 *                   但愿老死电脑间，不愿鞠躬老板前；
 *                   奔驰宝马贵者趣，公交自行程序员。
 *                   别人笑我忒疯癫，我笑自己命太贱；
 *                   不见满街漂亮妹，哪个归得程序员？
*/

int main()
{
	solve(); return 0;
}
```

## mingw 配置

### 旧版 mingw 配置:

先下载 「[my_mingw](https://media.githubusercontent.com/media/huaxv-code/huaxv-note/hutao/my_mingw.zip)」

解压缩后找到路径：`my_mingw/bin` 将 `bin` 目录添加进环境变量里，这样我们就可以在命令行内直接调用 `g++.exe、gcc.exe、gdb.exe` 工具编译我们的代码了

### 借助 msys2 包管理工具

1. 去官网下载 [msys2](https://www.msys2.org/) 或者在百度网盘里：链接：[百度网盘](https://pan.baidu.com/s/1x-uHTjnDDzizx-787W-wRA?pwd=1111)  提取码：1111
2. 打开 `msys2.exe` 执行下述命令：
   ```c++
	pacman -Syu --disable-download-timeout
	pacman -Syu --disable-download-timeout
	pacman -S mingw-w64-x86_64-gcc  --disable-download-timeout
	pacman -S mingw-w64-x86_64-make  --disable-download-timeout
	pacman -S mingw-w64-x86_64-gdb  --disable-download-timeout
	pacman -Syu --disable-download-timeout
   ```
3. 设置环境变量为 mingw 下的 bin 目录

## sublime 配置

先下载 「[my_sublime](https://github.com/huaxv-code/huaxv-note/raw/hutao/my_sublime.zip)」

解压缩后双击 `sublime_text.exe` 该程序就是我们要使用的程序

### 配置 `g++` 编译环境

跟着路径点击 ：`Tools -> Build System -> New Build System ...`

将里面的内容全删掉，粘贴代码：

```c++ title="g++.sublime-build"
{
	"cmd": ["g++", "${file}", "-o", "${file_path}/${file_base_name}"],
	"file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
	"working_dir": "${file_path}",
	"selector": "source.c, source.c++",

	"variants":
	[
		{
			"name": "Run",
			"cmd": ["cmd", "/c", "g++", "${file}", "-o", "${file_path}/${file_base_name}", "&&", "cmd", "/c", "${file_path}/${file_base_name}"]
		},
		{
			"name": "RunInCommand",
			"cmd": ["cmd", "/c", "g++", "${file}", "-o", "${file_path}/${file_base_name}", "&&", "start", "cmd", "/c", "${file_path}/${file_base_name} & pause"]
		}
	]
}
```

然后保存到路径：`my_sublime/Data/Packages/User` 下，文件名为：`g++.sublime-build`

### 配置用户代码片段

点击路径：`Tools -> Developer -> New snippet`

将打开的文件内容全都删掉，然后粘贴：

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

保存到目录：`my_sublime/Data/Packages/User` 下，你也可以在该目录下创建一个文件夹：`snippet`，然后点击保存到该文件夹内，保存的文件名为：`code.sublime-snippet`

### 多窗口

```c++
view -> Groups -> New Group

view -> word wrap // 换行

view -> SideBar -> show SideBar / Hide SideBar // 打开或关闭资源窗口。
```

## python 之禅

``` text
>>> import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!

Python之禅 by Tim Peters

优美胜于丑陋（Python 以编写优美的代码为目标）
明了胜于晦涩（优美的代码应当是明了的，命名规范，风格相似）
简洁胜于复杂（优美的代码应当是简洁的，不要有复杂的内部实现）
复杂胜于凌乱（如果复杂不可避免，那代码间也不能有难懂的关系，要保持接口简洁）
扁平胜于嵌套（优美的代码应当是扁平的，不能有太多的嵌套）
间隔胜于紧凑（优美的代码有适当的间隔，不要奢望一行代码解决问题）
可读性很重要（优美的代码是可读的）
即便假借特例的实用性之名，也不可违背这些规则（这些规则至高无上）
不要包容所有错误，除非你确定需要这样做（精准地捕获异常，不写 except:pass 风格的代码）
当存在多种可能，不要尝试去猜测
而是尽量找一种，最好是唯一一种明显的解决方案（如果不确定，就用穷举法）
虽然这并不容易，因为你不是 Python 之父（这里的 Dutch 是指 Guido ）
做也许好过不做，但不假思索就动手还不如不做（动手之前要细思量）
如果你无法向人描述你的方案，那肯定不是一个好方案；反之亦然（方案测评标准）
命名空间是一种绝妙的理念，我们应当多加利用（倡导与号召）
```

## 一些资源网站

[TDM-GCC](https://jmeubank.github.io/tdm-gcc/articles/2021-05/10.3.0-release)

[cp editor](https://cpeditor.org/zh/)

[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/insiders/)

[csacademy 画图论](https://csacademy.com/app/graph_editor/)