## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/task-scheduler/1"> Task Scheduler </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int leastInterval(int N, int K, vector<char> &tasks) {
        int ans=N;
        map<char,int>mp;
        int idle=0;
        int mx=0;
        for(int i=0;i<N;i++){
            mp[tasks[i]]++;
            mx=max(mx,mp[tasks[i]]);
        }
           idle=(mx-1)*K+(mx-1);
      
        for(auto x:mp){
          idle-=min(mx-1,x.second);
    
        }
       return (idle>0)?(ans+idle):(ans);
    }
</pre>
