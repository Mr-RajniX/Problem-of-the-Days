## Problem of the Day - [<a href="https://leetcode.com/problems/longest-zigzag-path-in-a-binary-tree/"> 1372. Longest ZigZag Path in a Binary Tree </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    int maxLength=0;
    void solve(TreeNode* root,int dir,int currLength){
        if(!root) return;
        maxLength=max(maxLength,currLength);
        solve(root->left,0,dir?currLength+1:1);
        solve(root->right,1,dir?1:currLength+1);
    }
    int longestZigZag(TreeNode* root) {
        solve(root,0,0);
        solve(root,1,0);
        return maxLength;
    }
</pre>
