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


#### ⭐<ins>Solution Function Code #2</ins> -

     vector<int> topKFrequent(vector<int>& nums, int k) {
             unordered_map<int, int> occurences;
             for (const auto num : nums) occurences[num]++;

             int smallest = INT_MAX, largest = INT_MIN;
             for (const auto& occ : occurences) {
                 smallest = std::min(occ.second, smallest);
                 largest = std::max(occ.second, largest);
             }

             int delimiter = (largest + smallest) / 2;
             while (delimiter >= smallest && delimiter <= largest) {
                 int count = 0;
                 for (const auto& occ : occurences) {
                     if (occ.second >= delimiter) count++;
                 }
                 if (count == k) break;
                 else if (count < k) {
                     largest = delimiter;
                 } else {
                     smallest = delimiter + 1;
                 }
                 delimiter = (largest + smallest) / 2;
             }
             vector<int> ret;
             for (const auto& occ : occurences)
                 if (occ.second >= delimiter) ret.emplace_back(occ.first);
             // Special cases eg. [1, 2] and k=1
             if (ret.size() > k) {
                 std::sort(ret.begin(), ret.end());
                 ret.erase(ret.begin() + k, ret.end());
             }
             return ret;
         }
