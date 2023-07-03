## Problem of the Day - [<a href="https://leetcode.com/problems/time-needed-to-inform-all-employees/"> 1376. Time Needed to Inform All Employees </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int numOfMinutes(int n, int headID, vector<int>& manager, vector<int>& informTime) {
        vector<int> arr[n];
        int ans = 0;
        for(int i = 0; i < n; i++){
            if(manager[i] != -1 ) {
                arr[manager[i]].push_back(i);
            }
        }

        queue<pair<int, int>> q;
        q.push({headID, informTime[headID]});

        while(!q.empty()){
            int si = q.size();
            for(int i = 0; i < si; i++){
                auto t = q.front();
                q.pop();

                for(auto x: arr[t.first]){
                    if(informTime[x] == 0){
                        ans = max(ans, t.second);
                    }else{
                        q.push({x, t.second + informTime[x]});
                    }
                }
            }
        }
        return ans;
    }
</pre>
