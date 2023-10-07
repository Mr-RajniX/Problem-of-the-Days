### Problem of the Day : [1337. The K Weakest Rows in a Matrix](https://leetcode.com/problems/the-k-weakest-rows-in-a-matrix/)

#### Solution :
<pre>
  vector< int> kWeakestRows(vector< vector< int>>& mat, int k) {
        vector< pair< int, int >> sum ;
        for(int i = 0; i < mat.size(); i++){
            int s = 0;
            for(int j = 0; j < mat[0].size(); j++){
                s += mat[i][j];
            } sum.push_back({s, i});
        }
        sort(sum.begin(), sum.end());
        vector< int> ans;
        for(int i= 0; i < k; i++)
            ans.push_back(sum[i].second);
        
        return ans;
    }
</pre>
