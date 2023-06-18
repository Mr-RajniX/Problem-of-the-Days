## Problem of the Day - [<a href="https://leetcode.com/problems/minimize-maximum-of-array/description/"> 2439. Minimize Maximum of Array </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    int minimizeArrayValue(vector<int>& A) {
        long sum = 0, res = 0;
        for (int i = 0; i < A.size(); ++i) {
            sum += A[i];
            res = max(res, (sum + i) / (i + 1));
        }
        return res;
    }
</pre>
