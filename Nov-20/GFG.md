#### Problem of the Day : [K Sum Paths](https://www.geeksforgeeks.org/problems/k-sum-paths/1)

#### Solution :
<pre>
  int sumK(Node *root,int k){
        unordered_map< int,int> f;
        f[0] = 1;        
        long long ans = 0;
        const long long mod = 1e9 + 7;
        function< void(Node *, int)> dfs = [&](Node * node, int sum) {
            if(node == nullptr)
                return 0;                
            sum += node -> data;            
            if(f.find(sum - k) != f.end())
                ans = (ans + f[sum - k]) % mod;
            ++f[sum];            
            dfs(node -> left, sum);
            dfs(node -> right, sum);                
            --f[sum];            
            if(f[sum] == 0)
                f.erase(sum);
        };        
        dfs(root, 0);        
        return ans;
    }
</pre>
