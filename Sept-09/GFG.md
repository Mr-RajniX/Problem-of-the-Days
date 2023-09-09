### Problem of the Day : [Kth largest element in BST](https://practice.geeksforgeeks.org/problems/kth-largest-element-in-bst/1)

#### Solution :
<pre>
  int kthLargest(Node *root, int K){
        vector< int> v;
        inorderTraverse(root, v);
        sort(v.begin(), v.end());
        return v[v.size() - K];
    }
    void inorderTraverse (Node *root, vector< int> &v){
        if(root == NULL) return;
        inorderTraverse(root->left, v);
        v.push_back(root->data);
        inorderTraverse(root->right, v);
    }
</pre>
