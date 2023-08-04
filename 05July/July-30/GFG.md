### Problem of the Day : [Inorder Successor in BST](https://practice.geeksforgeeks.org/problems/inorder-successor-in-bst/1)

#### Solution :
<pre>
  Node * inOrderSuccessor(Node *root, Node *x){
        Node* successor = nullptr;
        
        while (root) {
            if (x->data < root->data) {
                successor = root;
                root = root->left;
            } 
            else root = root->right;
        }
        return successor;
    }
</pre>
