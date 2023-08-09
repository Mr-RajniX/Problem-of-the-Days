### Problem of the Day : [Longest Common Subsequence](https://practice.geeksforgeeks.org/problems/longest-common-subsequence-1587115620/1)

#### Solution :
<pre>
  int lcs(int n, int m, string s1, string s2){
        // your code here
         vector< int >prev(m+1,0),curr(m+1,0);
        for(int i=0;i<=n;i++){
            for(int j=0;j<=m;j++){
                if(i==0 || j==0) continue;
                if(s1[i-1]==s2[j-1]) curr[j]=1+prev[j-1];
                else curr[j]=max(prev[j],curr[j-1]);
            }
            prev=curr;
        }
        return prev[m];
    }
</pre>
