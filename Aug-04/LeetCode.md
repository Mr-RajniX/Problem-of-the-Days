### Problem of the Day : [139. Word Break](https://leetcode.com/problems/word-break/)

#### Solution :
<pre>
  bool solve(string &s, map< string,bool >& mp, int ind, string temp,map< pair< int,string >,bool >&dp){
        if(ind == s.length() && temp == "") return true;
        if(ind == s.length()) return false;
        if(dp.find({ind,temp})!=dp.end()) return dp[{ind,temp}];
        bool ans = false;
        temp+=s[ind];
        if(mp.find(temp)!=mp.end()){
            ans = solve(s,mp,ind+1,"",dp);
        }
        ans = ans || solve(s,mp,ind+1,temp,dp);
        
        return dp[{ind,temp}] = ans;
    }

    bool wordBreak(string s, vector< string >& wordDict) {
        map< string,bool >mp;
        map< pair< int,string >,bool > dp;
        for(auto word: wordDict) mp[word] = true;
        return solve(s,mp,0,"",dp);
    }
</pre>
