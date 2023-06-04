## Problem of the Day - [<a href="https://leetcode.com/problems/number-of-provinces/"> 547. Number of Provinces </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int visited[205];
    void check(vector<int> v[],int itr){
        if(visited[itr]) 
            return;
        visited[itr]=1;
        for(int i=0;i < v[itr].size();i++)
            check(v,v[itr][i]);

        return;
    }

    int findCircleNum(vector<vector<int>>& isConnected) {
        int ans=0;
        vector<int> v[isConnected.size()];
        for(int i=0;i < isConnected.size();i++)
            for(int j=0;j < isConnected[i].size();j++)
                if(isConnected[i][j])v[i].push_back(j);
        for(int i=0;i < isConnected.size();i++)
            if(!visited[i]){
                check(v,i);
                ans++;
            }
        return ans;
    }
</pre>
