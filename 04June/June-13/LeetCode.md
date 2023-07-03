## Problem of the Day - [<a href="https://leetcode.com/problems/equal-row-and-column-pairs/"> 2352. Equal Row and Column Pairs </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int equalPairs(vector<vector<int>>& v) {
        int n=v.size();
        int r=0;
        vector<vector<int>>c=v;
        for(int i=0;i < n;i++){
            for(int j=i;j < n;j++)swap(v[i][j],v[j][i]);
        }
        for(int i=0;i < n;i++){
            for(int j=0;j < n;j++){
                if(v[i]==c[j])r++;
            }
        }
        return r;
    }
</pre>
