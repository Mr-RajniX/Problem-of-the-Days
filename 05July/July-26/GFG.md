### Problem of the Day : [Kth Ancestor in a Tree](https://practice.geeksforgeeks.org/problems/kth-ancestor-in-a-tree/1)

#### Solution :
<pre>
  Node* dfs(Node*root, int& k, int node){
  if(root==NULL) return NULL;
  if(root->data==node) return root;

  Node* leftAns = dfs(root->left,k, node);
  if(leftAns != NULL){
    k--;
    if(k<=0){
      k = INT_MAX;
      return root;
    }
    return leftAns;
  }
  
  
  Node* rightAns = dfs(root->right, k, node);
  if(rightAns != NULL){
    k--;
    if(k<=0){
      k=INT_MAX;
      return root;
    }
    return rightAns;
  }
  return NULL;
}

int kthAncestor(Node *root, int k, int node){
  Node* ans = dfs(root, k, node);
  if(ans == NULL || ans->data == node)
    return -1;
  return ans->data;
}
</pre>
