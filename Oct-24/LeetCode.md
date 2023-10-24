#### Problem of the Day : [515. Find Largest Value in Each Tree Row](https://leetcode.com/problems/find-largest-value-in-each-tree-row/)

#### Solution :
<pre>
  vector< int> largestValues(TreeNode* root) {
        map< int, int> mp;
        queue< pair< TreeNode*, int>> que;
        que.push({root, 0});

        while(!que.empty()){
          int val = que.front().second;
          TreeNode* node = que.front().first;
          que.pop();

          if(node == NULL)
            continue;
          
          if(mp.find(val) == mp.end())
            mp[val] = node->val;
          else
            mp[val] = max(mp[val], node->val);

          que.push({node->left, val+1});
          que.push({node->right, val+1});
        }

        vector < int> ans;
        for(auto x: mp)
          ans.push_back(x.second);

        return ans;
    }
</pre>
