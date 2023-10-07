### Problem of the Day : [Check if Tree is Isomorphic](https://practice.geeksforgeeks.org/problems/check-if-tree-is-isomorphic/1)

#### Solution :
<pre>
  bool isIsomorphic(Node *root1,Node *root2){
     if(root1 == NULL && root2 == NULL){
           return true;
       }
       if(root1 == NULL && root2 != NULL){
           return false;
       }
       if(root1 != NULL && root2 == NULL){
           return false;
       }
       if(root1->data != root2->data){
           return false;
       }
       return (isIsomorphic(root1->left, root2->left) && isIsomorphic(root1->right, root2->right)) || (isIsomorphic(root1->left, root2->right) && isIsomorphic(root1->right, root2->left));
    }
</pre>
