## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/camelcase-pattern-matching2259/1"> CamelCase Pattern Matching </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  vector<string> CamelCase(int N, vector<string> Dictionary, string Pattern){
        vector<string> ans;
        for (auto &s : Dictionary){
            int j = 0;
            for (int i = 0; i < s.length(); i++){
                if (s[i] >= 'A' && s[i] <= 'Z'){
                    if (s[i] != Pattern[j++]){
                        break;
                    }
                    if (j == Pattern.length()){
                        ans.push_back(s);
                        break;
                    }
                }
            }
        }
        if(ans.size() == 0)
            ans.push_back({"-1"});
        return ans;
    }
</pre>
