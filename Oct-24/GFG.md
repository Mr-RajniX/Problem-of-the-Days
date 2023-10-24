#### Problem of the Day : [Palindromic Partitioning](https://practice.geeksforgeeks.org/problems/palindromic-patitioning4845/1)

#### Solution :
<pre>
  int palindromicPartition(string str){
        int st = 0;
        int n = str.size();
        vector<int> dp(n+1, 0);
        
        for(int i = n-1; i >= 0; i--){
            int ans = (int)1e9;
            for(int k = i; k < n; k++){
                if(isPalindrome(str, i, k) == true){
                    int cur = 1 + dp[k+1];
                    ans = min(ans, cur);
                }
            }
            dp[i] = ans;
        }
        return dp[0]-1;
    }
    bool isPalindrome(string String, int i, int j){
        while (i < j) {
            if (String[i] != String[j])
                return false;
            i++;
            j--;
        }
        return true;
    }
</pre>
