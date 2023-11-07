### Problem of the Day : [Height of Binary Tree](https://practice.geeksforgeeks.org/problems/height-of-binary-tree/1)

#### Solution :
<pre>
  int height(struct Node* node){
        return (!node) ? 0 : max(height(node->left), height(node->right)) + 1;
    }
</pre>
