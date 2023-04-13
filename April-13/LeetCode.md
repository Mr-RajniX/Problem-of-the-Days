## Problem of the Day - [<a href="https://leetcode.com/problems/validate-stack-sequences/description/"> 946. Validate Stack Sequences </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    bool validateStackSequences(vector<int> &push, vector<int> &pop){
        int i = 0, j = 0, k = 0, n = push.size();
        while (k < n){
            push[i] = push[k];
            i++, k++;
            while (i > 0 && push[i - 1] == pop[j])
                --i, ++j;
        }
        return i == 0;
    }
</pre>
