## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/d894706c496da5c5a4f45b0360c7f4164c516f83/1"> Powerfull Integer </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int powerfullInteger(int n,vector<vector<int>> &intervals,int k){
        map<int,int> m;
        for(auto i: intervals){
            m[i[0]]++;
            m[i[1]+1]--;
        }
        int count=0,pcount=-1,ans=-1;
        for(auto i: m){
            count+=i.second;
            if(count>=k)
                ans=i.first;
            else if(pcount>=k)
                ans=i.first-1;
            pcount=count;
        }
        return ans;
    }
</pre>
