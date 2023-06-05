## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/find-the-closest-element-in-bst/1"> Find the Closest Element in BST </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int minDiff(Node *root, int K){
        if(root == NULL)
            return 1e9;
        return min({abs(K-root->data),minDiff(root->left,K),minDiff(root->right,K)});
    }
</pre>
