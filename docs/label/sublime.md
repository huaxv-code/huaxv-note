# sublime 配置

## g++.sublime-build

> C:\Users\huaxv\AppData\Roaming\Sublime Text\Packages\User\

??? note "g++.sublime-build"

    ```c++
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

## mycode.sublime-snippet

> C:\Users\huaxv\AppData\Roaming\Sublime Text\Packages\User\snippet

??? note "mycode.sublime-snippet"
    ```html
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
        ifstream fi("./lrq.in");
        ofstream fo("./lrq.out");
        if (fi.is_open() && fo.is_open())
        {
            fo << "start running ..." << endl;
            fo.close();
            fi.close();
            for (long long i = 1; i <= 400000000; i++)
                ;
            FILE *fin = freopen("./lrq.in", "r", stdin);
            FILE *fout = freopen("./lrq.out", "w", stdout);
            solve();
            fclose(fin);
            fclose(fout);
        }
        else
        {
            solve();
        }

        return 0;
    }
    ]]></content>
        <!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
        <!-- <tabTrigger>hello</tabTrigger> -->
        <!-- Optional: Set a scope to limit where the snippet will trigger -->
        <!-- <scope>source.python</scope> -->
        <tabTrigger>mycode</tabTrigger>
    </snippet>
    ```