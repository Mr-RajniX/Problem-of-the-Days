## Problem of the Day - [<a href="https://leetcode.com/problems/top-k-frequent-elements/"> 347. Top K Frequent Elements </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     vector<int> topKFrequent(vector<int>& nums, int k) {
          unordered_map<int,int> mp;
          priority_queue<vector<int>,vector<vector<int>>,greater<vector<int>>> pq;
          for(auto &i: nums){
              mp[i]++;
          }
          for(auto &i: mp){
              pq.push({i.second,i.first});
              if(pq.size()>k)pq.pop();
          }
          vector<int> ans;
          while(!pq.empty()){
              ans.push_back(pq.top()[1]);
              pq.pop();
          }
          return ans;
      }

