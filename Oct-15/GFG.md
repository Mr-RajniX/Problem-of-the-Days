#### Problem of the Day : [Normal BST to Balanced BST](https://practice.geeksforgeeks.org/problems/normal-bst-to-balanced-bst/1)

#### Solution :
<pre>
  Node* buildBalancedTree(Node* root){
    	vector< Node *>v;
        Inorder(root,v);
        int start=0;
        int end=v.size()-1;
        return solve(v,start,end);
    }
    void Inorder(Node *root,vector<Node *>&v){
        if(root==NULL) return;
        Inorder(root->left,v);
        v.push_back(root);
        Inorder(root->right,v);
    }
    Node *solve(vector< Node *>&v,int start,int end){
        if(start > end) return NULL;
        int mid=(start+end)/2;
        Node *root=v[mid];
        root->left=solve(v,start,mid-1);
        root->right=solve(v,mid+1,end);
        return root;
    }
</pre>
