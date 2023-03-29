## Problem of the Day - [<a href="https://leetcode.com/problems/reducing-dishes/description/"> 1402. Reducing Dishes </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int maxSatisfaction(vector<int>& satisfaction) {
        vector<int>v=satisfaction;
        sort(v.begin(),v.end());
        reverse(v.begin(),v.end());
        int sum=0,ans=0;
        for(int i=0;i<v.size();i++){
            if(sum+v[i]>0){
                ans+=sum+v[i];
                sum+=v[i];
            }
        }
        return ans;
    }
</pre>
