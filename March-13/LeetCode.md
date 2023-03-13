## Problem of the Day - [<a href="https://leetcode.com/problems/symmetric-tree/description/"> 101. Symmetric Tree </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    bool issame(TreeNode* root1 , TreeNode* root2){
        if(root1==NULL && root2==NULL){
        return true;
        }
        if(root1==NULL || root2==NULL){
        return false;
        }
        if(root1->val!=root2->val){
            return false;
        }        
        return issame(root1->left,root2->right) && issame(root1->right,root2->left);
    }
    bool isSymmetric(TreeNode* root) {
        if(root->left ==NULL && root->right==NULL){
            return true;
        }    
        bool ans=issame(root->left,root->right);
        return ans;
    }
</pre>
