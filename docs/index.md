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