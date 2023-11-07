### Problem of the Day : [Count number of substrings](https://practice.geeksforgeeks.org/problems/count-number-of-substrings4528/1)

#### Solution :
<pre>
  long long int substrCount (string s, int k) {
    	int n = s.size();
        return solve(s, n, k) - solve(s, n, k - 1);
    }
    long long int solve(string &str, int n, int k){
        int i = 0, j = 0;
        long long int ans = 0;
        long long int dist = 0;
        int hash_cnt[26] = {0};
        while (j < n){
            hash_cnt[str[j] - 'a']++;
            if (hash_cnt[str[j] - 'a'] == 1)
                dist++;
            while (dist > k){
                hash_cnt[str[i] - 'a']--;
                if (hash_cnt[str[i] - 'a'] == 0)
                    dist--;
                i++;
            }
            ans += j - i + 1;
            j++;
        }
        return ans;
    }
</pre>
