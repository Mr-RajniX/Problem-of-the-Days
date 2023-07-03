## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/find-kth-permutation-0932/1"> Find Kth permutation </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  string kthPermutation(int n, int k){
        string ans="";
        for(int i=1;i<=n;i++){
            ans+=to_string(i);
        }
        k--;
        while(k--){
            next_permutation(ans.begin(),ans.end());
        }
        return ans;
    }
</pre>
