#### Problem of the Day : [Floor in BST](https://practice.geeksforgeeks.org/problems/floor-in-bst/1)

#### Solution :
<pre>
  int mini=INT_MIN;
    int floor(Node* root, int x) {
        if(!root) return -1;
        if(root->data==x)
            mini=x;        
        if(root->data < x){
            mini=max(root->data, mini);
            floor(root->right, x);
        }else
            floor(root->left, x);
        
        return mini==INT_MIN?-1:mini;
    }
</pre>
