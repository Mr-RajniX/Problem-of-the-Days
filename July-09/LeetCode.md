### Problem of the day : [2272. Substring With Largest Variance](https://leetcode.com/problems/substring-with-largest-variance/)

#### Solution : #1
<pre>
  int largestVariance(string s) {
        vector< int > arr(26);
        for(auto x : s) 
            arr[x - 'a']++; 
        int ans = 0; 
        for(char i = 'a'; i <= 'z'; i++) { 
            for(char j = 'a'; j <= 'z'; j++) {
                if(j == i || arr[i - 'a'] == 0 || arr[j - 'a'] == 0)
                    continue;
                for(int k = 1; k <= 2; k++) { 
                    int A1 = 0; 
                    int A2 = 0; 
                    for(auto x : s) {
                        if(x == i)
                            A1++; 
                        if(x == j)
                            A2++; 
                        if(A2 > A1) {
                            A1 = 0;
                            A2 = 0; 
                        }
                        if(A1 > 0 && A2 > 0)
                            ans = max(ans, A1 - A2);
                    }
                    reverse(s.begin(), s.end()); 
                }
            }
        }
        return ans;
    }
</pre>

#### Solution : #2
<pre>
  int largestVariance(string s) {
    int res = 0;
    unordered_set< char > unique(begin(s), end(s));
    for (char a : unique)
        for (char b : unique) {
            int var = 0, has_b = 0, first_b = 0;
            for (auto ch : s) {
                var += ch == a;
                if (ch == b) {
                    has_b = true;
                    if (first_b && var >= 0)
                        first_b = false;
                    else if (--var < 0) {
                        first_b = true;
                        var = -1;
                    }
                }
                res = max(res, has_b ? var : 0);
            }
        }
    return res;
}
</pre>
