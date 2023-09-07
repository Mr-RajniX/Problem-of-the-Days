### Problem of the Day : [Minimum Multiplications to reach End](https://practice.geeksforgeeks.org/problems/minimum-multiplications-to-reach-end/1)

#### Solution : 
<pre>
  int minimumMultiplications(vector< int> & arr, int start, int end) {
        queue< int> q;
        q.push(start);
        int mod = 100000;
        vector< int> vis(mod, 0);
        vis[start] = 1;
        
        
        int ans = 0;
        while(!q.empty()){
            int sz = q.size();
            for(int i=0; i < sz; i++){
                int node = q.front();
                q.pop();
                if(node == end) return ans;
                
                for(auto id: arr) {
                    start = id * node;
                    start %= mod;
                    if(vis[start] == 0){
                        vis[start] = 1;
                        q.push(start);
                    }
                }
            }
            ans++;
        }
        return -1;
    }
</pre>
