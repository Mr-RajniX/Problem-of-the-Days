### Problem of the Day : [Median of BST](https://practice.geeksforgeeks.org/problems/median-of-bst/1)

#### Solution :
<pre>
  void inorder(struct Node* root,vector< float > &vec){
    if(root==NULL){
        return ;
    }
    inorder(root->left,vec);
    vec.push_back(root->data);
    inorder(root->right,vec);
}
float findMedian(struct Node *root)
{
      //Code here
      vector< float > vec;
      inorder(root,vec);
      int n=vec.size();
      if(n%2==0){
           return ((vec[n/2]+vec[n/2 -1])/2);
          
      }
      else{
          return vec[n/2];
          
      }
}


</pre>
