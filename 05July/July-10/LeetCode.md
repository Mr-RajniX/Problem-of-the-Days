### Problem of the Day : [111. Minimum Depth of Binary Tree](https://leetcode.com/problems/minimum-depth-of-binary-tree/)

#### Solution :
<pre>
  int minDepth(TreeNode* root) {
        if(root == NULL) return 0;
        int leftchild = minDepth(root->left);
        int rightchild = minDepth(root->right);
        if(root->left && root->right) return min(leftchild+1,rightchild+1);
        return max(leftchild+1, rightchild+1);
    }
</pre>

#### Solution : #2 [BFS]
<pre>
  int minDepth(TreeNode* root) {
        if (root==NULL) 
            return 0;

        int mndepth = 0;
        queue< TreeNode* > q;
        q.push(root);
        while (!q.empty()) {
            int size = q.size();
            mndepth++;
          while (size--) {
                TreeNode* cur = q.front(); 
                q.pop();
                if (cur->left)
                    q.push(cur->left);
                if (cur->right)
                    q.push(cur->right);
                if (cur->left == NULL && cur->right == NULL) {
                    return mndepth;
                }
            }
        }
        return mndepth;
    }
</pre>
