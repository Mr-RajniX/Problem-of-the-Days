## Problem of the Day - [<a href="https://leetcode.com/problems/sum-root-to-leaf-numbers/description/"> 129. Sum Root to Leaf Numbers </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    void dfs(TreeNode *root, long long &ans , long long tmp){
        if(root->left== NULL && root->right==NULL){
            tmp = tmp*10 + root->val;
            ans+=tmp;
            return;
        }
        tmp = tmp*10 + root->val;
        if(root->left) dfs(root->left,ans,tmp);
        if(root->right) dfs(root->right,ans,tmp);
    }

    int sumNumbers(TreeNode* root) {
        long long ans =0;
        dfs(root,ans,0);
        return int(ans);
    }
</pre>
