## Problem of the Day - [<a href="https://leetcode.com/problems/check-completeness-of-a-binary-tree/description/"> 958. Check Completeness of a Binary Tree </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    bool isCompleteTree(TreeNode* root) {
        queue<TreeNode*>q;
        q.push(root);
        bool nullfound = false;
        while(!q.empty()){   
            TreeNode *curr = q.front();
            q.pop();
            if(curr == NULL)
            nullfound = true;
            else{
                if(nullfound)
                return false;
                else{
                    q.push(curr->left);
                    q.push(curr->right);
                }
            }            
        }
        return true;
    }
</pre>
