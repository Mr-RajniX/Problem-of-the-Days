### Problem of the Day : [Insert a node in a BST](https://practice.geeksforgeeks.org/problems/insert-a-node-in-a-bst/1)

#### Solution :
<pre>
  Node* insert(Node* node, int data) {
            if(!node){
                Node* newNode = new Node(data);
                return newNode;
            }
            if(node->data > data){
                node->left = insert(node->left, data);
            }
            else if(node->data < data){
                node->right = insert(node->right, data);
            }
            return node;
    }
</pre>
