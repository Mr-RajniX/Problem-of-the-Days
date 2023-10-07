### Problem of the Day : [Binary Tree to BST](https://practice.geeksforgeeks.org/problems/binary-tree-to-bst/1)

#### Solution :
<pre>
  Node *binaryTreeToBST (Node *root){
        priority_queue< int, vector< int>, greater< int>> pq;
        traverse(root, pq);
        inorder(root, pq);
        return root;
    }
    void traverse(Node* root,  priority_queue < int, vector< int>, greater< int>> &pq){
        if(!root) return;
        pq.push(root->data);
        traverse(root->left, pq);
        traverse(root->right, pq);
    }
    
    void inorder(Node* root,  priority_queue < int, vector< int>, greater< int>> &pq){
        if(!root) return;
        inorder(root->left, pq);
        root->data = pq.top();
        pq.pop();
        inorder(root->right, pq);
    }
</pre>
