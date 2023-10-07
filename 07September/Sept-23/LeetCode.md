### Problem of the Day : [1048. Longest String Chain](https://leetcode.com/problems/longest-string-chain/)


#### Solution :
<pre>
  static bool cmp(const string &s1, const string &s2) {
        return s1.length() < s2.length();
    }

    int longestStrChain(vector< string>& words) {
        sort(words.begin(), words.end(), cmp);
        unordered_map< string, int> ump;
        int ans = 0;
        for (string w : words) {
            int longest=0;
            for (int i = 0; i < w.length(); i++) {
                string sub = w;
                sub.erase(i, 1);
                longest = max(longest,ump[sub]+1);
            }
            ump[w] = longest;
            ans = max(ans,longest);
        }
        return ans;
    }
</pre>
