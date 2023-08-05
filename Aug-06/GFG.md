### Problem of the Day : [String Permutations](https://practice.geeksforgeeks.org/problems/permutations-of-a-given-string-1587115620/1)

#### Solution :
<pre>
  void solve(int l,int r,string s,vector< string >&ans){
        if(l==r){
            ans.push_back(s);
            return;
        }
        for(int i=l;i<=r;i++){
            swap(s[l],s[i]);
            solve(l+1,r,s,ans);
            swap(s[l],s[i]);
        }
    }
    vector< string > permutation(string S){
        vector< string >ans;
        int n=S.size();
        solve(0,n-1,S,ans);
        sort(ans.begin(),ans.end());
        return ans;
    }
</pre>
