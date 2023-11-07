#### Problem of the Day : [Find Common Nodes in two BSTs](https://practice.geeksforgeeks.org/problems/print-common-nodes-in-bst/1)

#### Solution :
<pre>
  vector< int> ans;
    public: 
    bool find(Node *root, int val) {
        if(!root) return 0;
        if(root->data > val) return find(root->left,val);
        else if(root->data < val) return find(root->right,val);
        else return 1;
    }
    void helper(Node *root1, Node *root2) {
        if(!root1 or !root2) return ;
        helper(root1->left,root2);
        if(find(root2,(root1->data))) ans.push_back(root1->data);
        helper(root1->right,root2);
    }
    vector <int> findCommon(Node *root1, Node *root2)
    {
        ans.clear();
        helper(root1,root2);
        return ans;
    }
</pre>
