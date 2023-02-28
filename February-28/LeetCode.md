## Problem of the Day - [<a href="https://leetcode.com/problems/find-duplicate-subtrees/description/"> 652. Find Duplicate Subtrees </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    vector<TreeNode*> findDuplicateSubtrees(TreeNode* root) {
        unordered_map<string, int> frequency;
        vector<TreeNode*> result;
        findDuplicates(root, frequency, result);
        return result;
    }
    
private:
    string findDuplicates(TreeNode* node, unordered_map<string, int>& frequency, vector<TreeNode*>& result) {
        if (!node) {
            return "#";
        }        
        string leftIdentifier = findDuplicates(node->left, frequency, result);
        string rightIdentifier = findDuplicates(node->right, frequency, result);
        string identifier = to_string(node->val) + "," + leftIdentifier + "," + rightIdentifier;
        frequency[identifier]++;        
        if (frequency[identifier] == 2) {
            result.push_back(node);
        }
        
        return identifier;
    }
</pre>
