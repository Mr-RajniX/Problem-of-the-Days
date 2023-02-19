## Problem of the Day - [<a href="https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/description/"> 103. Binary Tree Zigzag Level Order Traversal </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    vector<vector<int>> zigzagLevelOrder(TreeNode* root) {
        vector<vector<int>>ans;
        queue<TreeNode*>q;

        if(!root)
            return ans;
        q.push(root);

        int ch=1;
        while(q.size())
        {
            int n=q.size();
            vector<int>v;
            for(int i=0;i<n;i++)
            {
                TreeNode* temp=q.front();
                v.push_back(temp->val);
                q.pop();

                if(temp->left)
                {
                q.push(temp->left);
                }
                if(temp->right)
                {
                q.push(temp->right);
                }
            }
            if(ch==1)
            {
            ans.push_back(v);
            ch=-1;
            }
            else
            {
                reverse(v.begin(),v.end());
                ans.push_back(v);
                ch=1;
            }
        }
        return ans;
    }
</pre>
