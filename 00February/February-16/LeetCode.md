## Problem of the Day - [<a href="https://leetcode.com/problems/maximum-depth-of-binary-tree/description/"> 104. Maximum Depth of Binary Tree </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    -> Beginner's Solution using Recursion :
        int maxDepth(TreeNode* root) {
            if(root == NULL) return 0;
            int left = maxDepth(root->left);
            int right = maxDepth(root->right);
            return max(left, right) + 1;
        }
        
     -> Solution in ShortCut way ^_~
         int maxDepth(TreeNode* root) {
            return root == NULL ? 0 :  max(maxDepth(root->left),  maxDepth(root->right) ) + 1;
         }
</pre>
