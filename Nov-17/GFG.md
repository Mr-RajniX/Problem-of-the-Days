#### Problem of the Day : [Binary Tree to CDLL](https://www.geeksforgeeks.org/problems/binary-tree-to-cdll/1)

#### Solution :
<pre>
    vector< Node*>vec;
    void inorder(Node* root){
        if(root==NULL)return;
        inorder(root->left);
        vec.push_back(root);
        inorder(root->right);
    }
    Node *bTreeToCList(Node *root)
    { 
      if(root==NULL)return root;
      inorder(root);
      Node*head=vec[0];
      Node*curr=vec[0];
      Node*prev=vec[0];
      for(int i=1;i < vec.size();i++){
          curr=vec[i];
          prev->right=curr;
          curr->left=prev;
          prev=curr;
      }
      head->left=prev;
      prev->right=head;
      return head;
    }
</pre>
