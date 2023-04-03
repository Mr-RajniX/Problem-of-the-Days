## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/9a88fe7ada1c49c2b3da7a67b43875e4a76aface/1"> Maximum Bipartite Matching </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    vector<int> match;
    vector<int> vis;
    bool solve(int p,vector<vector<int>>&g){
        for(int j=0;j<g[0].size();j++){
            if(g[p][j] && !vis[j]){
                vis[j]=1;
                if(match[j]==-1 || solve(match[j],g)){
                    match[j]=p;
                    return true;
                }
            }
        }
        return false;
    }

    int maximumMatch(vector<vector<int>>&G){
     // Code here
        int p=G.size();
        int j=G[0].size();
        match=vector<int>(j,-1);
        int res=0;
        for(int i=0;i<p;i++){
            vis=vector<int> (j,0);
            if(solve(i,G))  res++;
        }
        return res;
    }
</pre>
