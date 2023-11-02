#### Problem of the Day : [2265. Count Nodes Equal to Average of Subtree](https://leetcode.com/problems/count-nodes-equal-to-average-of-subtree/)

#### Solution :
<pre>
    int result = 0;
    int averageOfSubtree(TreeNode* root) {
        dfs(root);
        return result;
    }
    vector< int> dfs(TreeNode* node) {
        if (!node) {
            return {0, 0};
        }
        vector< int> left = dfs(node->left);
        vector< int> right = dfs(node->right);
        int currentSum = left[0] + right[0] + node->val;
        int currentCount = left[1] + right[1] + 1;
        if (currentSum / currentCount == node->val) {
            result++;
        }
        return {currentSum, currentCount};
    }
</pre>
