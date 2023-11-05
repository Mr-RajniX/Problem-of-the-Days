#### Problem of the Day : [Top K Frequent Elements in Array - |](https://www.geeksforgeeks.org/problems/top-k-frequent-elements-in-array/1)

#### Solution :
<pre>
  vector< int> topK(vector< int>& nums, int k) {
        vector< int>v;
        priority_queue< pair< int,int>>pq;
        unordered_map< int,int>mp;
        for(int i=0;i < nums.size();i++) 
        mp[nums[i]]++;
        
        for(auto it:mp){
            pq.push({it.second,it.first});
        }
        for(int i=0;i < k;i++){
            int d=pq.top().second;
            pq.pop();
            v.push_back(d);
        }
        return v;
    }
</pre>
