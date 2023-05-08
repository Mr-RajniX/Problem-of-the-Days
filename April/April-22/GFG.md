## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/5877fde1c8e1029658845cd4bc94066ac1d4b09b/1"> Smaller Sum </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   vector<long long> smallerSum(int n,vector<int> &arr){
        // Code here
        map<long long,long long> mp;
        for(auto x:arr) mp[x]++;
        unordered_map<long long,long long> mp1;
        long long sum=0;
        for(auto x:mp){
            mp1[x.first]=sum;
            while(x.second--){
                sum+=x.first;
            }
        }
        vector<long long> ans;
        for(auto x:arr){
            ans.push_back(mp1[x]);
        }
        return ans;
    }
</pre>
