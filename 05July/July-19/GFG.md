### Problem of the Day :[Longest Palindromic Subsequence](https://practice.geeksforgeeks.org/problems/longest-palindromic-subsequence-1612327878/1)

#### Solution :
<pre>
  int longestPalinSubseq(string A) {
        string rev = A;
        reverse(rev.begin(), rev.end());
        int n = A.size();
        vector<int> prev(n+1, 0), curr(n+1, 0);
        for(int i = 1; i <= n; i++)
        {
            for(int j = 1; j <= n; j++)
            {
                if(A[i-1] == rev[j-1]) curr[j] = 1 + prev[j-1];
                else curr[j] = max(curr[j-1],prev[j]);
            }
            prev = curr;
        }
        return prev[n];
    }
</pre>
