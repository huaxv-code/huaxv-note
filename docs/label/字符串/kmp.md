# kmp

??? note 

    ```c++
    int kmp(char s[], char c[])
    {
        int n = -1, m = -1, i, j;
        while (s[++ n]); while (c[++ m]);
        vector<int> ne(m + 1, 0);
        i = -1, j = 0, ne[0] = -1;
        while (j < m)
        {
            if (i == -1 || c[i] == c[j])
            {
                i ++, j ++; ne[j] = i;
            }
            else i = ne[i];
        }
        i = 0, j = 0;
        while (i < n && j < m)
        {
            if (j == -1 || s[i] == c[j]) i ++, j ++;
            else j = ne[j];
        }
        if (j == m) return i - j;
        else return -1;
    }
    ```