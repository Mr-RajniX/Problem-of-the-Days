## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/df12afc57250e7f6fc101aa9c272343184fe9859/1"> Good Subtrees </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   unordered_set<int> postorder(Node* root,int &ans,int k){
        if(root==NULL){
            unordered_set<int> st;
            return st;
        }
        unordered_set<int> leftSubtree = postorder(root->left,ans,k);
        unordered_set<int> rightSubtree = postorder(root->right,ans,k);
        unordered_set<int> Subtree;
        for(auto x:leftSubtree){
            Subtree.insert(x);
        }
        for(auto x:rightSubtree){
            Subtree.insert(x);
        }
        Subtree.insert(root->data);
        if(Subtree.size()<=k){
            ans++;
        }
        return Subtree;
    }
    int goodSubtrees(Node* root,int k){
        // Code here
        int ans=0;
        postorder(root,ans,k);
        return ans;
    }
</pre>
