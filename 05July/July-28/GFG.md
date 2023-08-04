### Problem of the Day : [Lowest Common Ancestor in a BST](https://practice.geeksforgeeks.org/problems/lowest-common-ancestor-in-a-bst/1)

#### solution :
<pre>
      Node* LCA(Node *root, int n1, int n2){
            if( root == NULL ) return NULL;
            int current = root -> data;
            if( current < n1 && current < n2) return LCA(root -> right, n1, n2);
            if( current > n1 && current > n2) return LCA(root -> left, n1, n2);
            return root;
        }
</pre>
