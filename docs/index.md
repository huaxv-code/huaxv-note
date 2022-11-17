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

## 刷题代码壳

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

## sublime 「g++」配置

```json title="g++.sublime-build"
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

## vscode setting 配置

```json title="settings.json"
{
    "explorer.confirmDelete": false,
    "markdown-preview-enhanced.previewTheme": "atom-dark.css", // markdown 主题
    "workbench.startupEditor": "none", // 主题
    "workbench.iconTheme": "eq-material-theme-icons", // 文件图标
    "editor.fontSize": 20, // 字体大小
    "terminal.integrated.fontSize": 16, // 命令行字体大小
    "editor.fontFamily": "Cascadia Code, Consolas, 'Courier New', monospace", // 字体样式
    "terminal.integrated.profiles.windows": {
        "PowerShell": {
            "source": "PowerShell",
            "icon": "terminal-powershell",
            "args": [
                "-NoExit",
                "chcp 65001"
            ],
        },
        "Command Prompt": {
            "path": [
                "${env:windir}\\Sysnative\\cmd.exe",
                "${env:windir}\\System32\\cmd.exe"
            ],
            "args": [
                "/K chcp 65001 >nul"
            ],
            "icon": "terminal-cmd"
        },
        "Git Bash": {
            "source": "Git Bash"
        }
    },
    "code-runner.runInTerminal": true,
    "git.confirmSync": false,
    "git.enableSmartCommit": true,
    "vsicons.dontShowNewVersionMessage": true,
    "terminal.integrated.enableMultiLinePasteWarning": false, // 在命令行中运行
    "code-runner.saveAllFilesBeforeRun": true,
    "code-runner.saveFileBeforeRun": true,
    "editor.stickyScroll.enabled": true,
    "git.autofetch": true,
    "workbench.colorTheme": "Noctis Uva",
    // "C_Cpp.default.compilerPath": "C:/mingw/mingw64/bin/gcc.exe",
    "C_Cpp.default.enableConfigurationSquiggles": false,
    "C_Cpp.default.intelliSenseMode": "windows-gcc-x64",
    "files.autoSave": "afterDelay",
    "editor.codeLensFontFamily": "Cascadia Code",
    "terminal.integrated.fontFamily": "Consolas",
    "explorer.confirmDragAndDrop": false,
    "explorer.compactFolders": false,
}
```

## vscode 代码片段

```json title="cpp.json"
{
	// Place your snippets for cpp here. Each snippet is defined under a snippet name and has a prefix, body and 
	// description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
	// $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the 
	// same ids are connected.
	// Example:
	"main" :{
		"prefix": "code",
		"body": [
			"#include<iostream>",
			"",
			"using namespace std;",
			"int debuggersum = 0;",
			"",
			"// 即使是不成熟的尝试，",
			"",
			"$0",
			"",
			"void solve(void) ",
			"{",
			"\t",
			"}",
			"",
			"// 也胜于胎死腹中的策略。",
			"",
			"int main(void)",
			"{",
			"    solve();",
			"    return 0;",
			"}"
		]
	},
	// "initfile": {
	// 	"prefix": "initfile",
	// 	"body": [
	// 		"#include<bits/stdc++.h>",
	// 		"",
	// 		"using namespace std;",
	// 		"int debuggersum = 0;",
	// 		"",
	// 		"// 即使是不成熟的尝试，",
	// 		"",
	// 		"$0",
	// 		"",
	// 		"void solve(void) ",
	// 		"{",
	// 		"\t",
	// 		"}",
	// 		"",
	// 		"// 也胜于胎死腹中的策略。",
	// 		"",
	// 		"int main(void)",
	// 		"{",
	// 		"    ifstream fin(\"./LinRQ.in\");",
	// 		"    ofstream fout(\"./LinRQ.out\");",
	// 		"    if (fin.is_open() && fout.is_open())",
	// 		"    {",
	// 		"        fout << \"start running ... ...\" << endl;",
	// 		"        for (long long i = 1; i <= 100000000; i ++);",
	// 		"        fout.close();",
	// 		"        for (long long i = 1; i <= 100000000; i ++);",
	// 		"        fout.open(\"./LinRQ.out\");",
	// 		"        auto a = fin.rdbuf();",
	// 		"        auto b = fout.rdbuf();",
	// 		"        auto c = cin.rdbuf();",
	// 		"        auto d = cout.rdbuf();",
	// 		"        cin.rdbuf(a);",
	// 		"        cout.rdbuf(b);",
	// 		"        solve();",
	// 		"        cin.rdbuf(c);",
	// 		"        cout.rdbuf(d);",
	// 		"        fin.close();",
	// 		"        fout.close();",
	// 		"    }",
	// 		"    else",
	// 		"    {",
	// 		"        ios::sync_with_stdio(false);",
	// 		"        cin.tie(nullptr);",
	// 		"        cout.tie(nullptr);",
	// 		"        solve();",
	// 		"    }",
	// 		"",
	// 		"    return 0;",
	// 		"}"
	// 	],
	// 	"description": "Log output to console"
	// },
	"initfile": {
		"prefix": "initfile",
		"body": [
			"#include <bits/stdc++.h>",
			"",
			"using namespace std;",
			"int debuggersum = 0;",
			"",
			"// 即使是不成熟的尝试，",
			"",
			"$0",
			"",
			"void solve(void)",
			"{",
			"    ",
			"}",
			"",
			"// 也胜于胎死腹中的策略。",
			"",
			"int main(void)",
			"{",
			"    ifstream fi(\"./LinRQ.in\");",
			"    ofstream fo(\"./LinRQ.out\");",
			"    if (fi.is_open() && fo.is_open())",
			"    {",
			"        fo << \"start running ...\" << endl;",
			"        fo.close();",
			"        fi.close();",
			"        for (long long i = 1; i <= 200000000; i++)",
			"            ;",
			"        FILE *fin = freopen(\"./LinRQ.in\", \"r\", stdin);",
			"        FILE *fout = freopen(\"./LinRQ.out\", \"w\", stdout);",
			"        solve();",
			"        fclose(fin);",
			"        fclose(fout);",
			"    }",
			"    else",
			"    {",
			"        solve();",
			"    }",
			"",
			"    return 0;",
			"}",
		]
	},
	"int main": {
		"prefix": "intmain",
		"body": [
			"int main(void)",
			"{",
			"    ifstream fin(\"./LinRQ.in\");",
			"    ofstream fout(\"./LinRQ.out\");",
			"    if (fin.is_open() && fout.is_open())",
			"    {",
			"        fout << \"start running ... ...\" << endl;",
			"        for (long long i = 1; i <= 100000000; i ++);",
			"        fout.close();",
			"        for (long long i = 1; i <= 100000000; i ++);",
			"        fout.open(\"./LinRQ.out\");",
			"        auto a = fin.rdbuf();",
			"        auto b = fout.rdbuf();",
			"        auto c = cin.rdbuf();",
			"        auto d = cout.rdbuf();",
			"        cin.rdbuf(a);",
			"        cout.rdbuf(b);",
			"        solve();",
			"        cin.rdbuf(c);",
			"        cout.rdbuf(d);",
			"        fin.close();",
			"        fout.close();",
			"    }",
			"    else",
			"    {",
			"        ios::sync_with_stdio(false);",
			"        cin.tie(nullptr);",
			"        cout.tie(nullptr);",
			"        solve();",
			"    }",
			"",
			"    return 0;",
			"}"
		],
		"description": "Log output to console"
	}
}
```