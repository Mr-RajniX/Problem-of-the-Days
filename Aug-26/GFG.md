### Problem of the day : [Longest K unique characters substring](https://practice.geeksforgeeks.org/problems/longest-k-unique-characters-substring0853/1)

#### Solution :
<pre>
  int longestKSubstr(string s, int k) {
        int n=s.size();
        int longest=-1;
        unordered_map<char,int>mp;
        int count=k;
        int i=0,j=0;
        while(j < n){
            mp[s[j]]++;
            if(mp.size()==k){
                longest=max(longest,j-i+1);
            }
            while(mp.size() > k){
                if(mp.find(s[i])!=mp.end()){
                    mp[s[i]]--;
                    if(mp[s[i]]==0) mp.erase(s[i]);
                }
                i++;
            }
           
            j++;
        }
        return longest;
    }
</pre>
