## Problem of the Day - [<a href="https://leetcode.com/problems/invert-binary-tree">226. Invert Binary Tree </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    TreeNode* invertTree(TreeNode* root) {
        if(root==NULL)
            return NULL;
        invertTree(root->left); 
        invertTree(root->right); 
       
        TreeNode* temp = root->left;
        root->left = root->right;
        root->right = temp;
        return root;
    }
</pre>
