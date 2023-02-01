## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/844b4fdcd988ac5461324d62d43f7892749a113c/1"> Distinct Coloring </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    long long int f(int ind,int N,int r[],int g[],int b[],int prev,vector<vector<long long int>>& dp){        
        if(ind==N) return 0;        
        if(dp[ind][prev]!=-1) return dp[ind][prev];        
        long long int taker=1e11,takeg=1e11,takeb=1e11;
        if(prev==0){
            taker=r[ind]+f(ind+1,N,r,g,b,1,dp);
            takeg=g[ind]+f(ind+1,N,r,g,b,2,dp);
            takeb=b[ind]+f(ind+1,N,r,g,b,3,dp);
        }else if(prev==1){
            takeg=g[ind]+f(ind+1,N,r,g,b,2,dp);
            takeb=b[ind]+f(ind+1,N,r,g,b,3,dp);
        }else if(prev==2){
            taker=r[ind]+f(ind+1,N,r,g,b,1,dp);
            takeb=b[ind]+f(ind+1,N,r,g,b,3,dp);
        }else{
            takeg=r[ind]+f(ind+1,N,r,g,b,1,dp);
            takeb=g[ind]+f(ind+1,N,r,g,b,2,dp);
        }
        return dp[ind][prev]=min(taker,min(takeb,takeg));
    }
    long long int distinctColoring(int N, int r[], int g[], int b[]){
        // code here 
        vector<vector<long long int>>  dp(N,vector<long long int>(4,-1));
        return f(0,N,r,g,b,0,dp);
    }
</pre>
