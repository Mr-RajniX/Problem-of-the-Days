## Problem of the Day - [<a href="https://leetcode.com/problems/minimum-absolute-difference-in-bst/"> 530. Minimum Absolute Difference in BST </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    int prev = INT_MAX;
    int ans = INT_MAX;    
    int getMinimumDifference(TreeNode* root) {
        inOrder(root);
        return ans;
    }    
    void inOrder(TreeNode* root) {
        if (root->left != nullptr)
            inOrder(root->left);        
        ans = std::min(ans, std::abs(root->val - prev));
        prev = root->val;        
        if (root->right != nullptr)
            inOrder(root->right);
    }
</pre>
