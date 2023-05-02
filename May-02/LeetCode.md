## Problem of the Day - [<a href="https://leetcode.com/problems/sign-of-the-product-of-an-array/"> 1822. Sign of the Product of an Array </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int arraySign(vector<int>& a) {
        int cnt = 0;
        for(int i = 0; i < a.size(); i++) 
        {
            if(a[i] == 0) return 0;
            if(a[i] < 0) cnt++;
        }
        return cnt%2 ? -1 : 1;
    }
</pre>
