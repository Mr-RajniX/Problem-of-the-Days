## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/6c4053871794c5e7a0817d7eaf88d71c4bb4c2bc/1"> Fixing Two swapped nodes of a BST </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    class Solution {
    public:
        void inorder(struct Node *r,vector<int>&v){
            if(r==NULL) return;
            inorder(r->left,v);
            v.push_back(r->data);
            inorder(r->right,v);
        }
        void modify(struct Node *&f,vector<int>&p,int &i){
            if(f==NULL) return;
            modify(f->left,p,i);
            f->data=p[i++];
            modify(f->right,p,i);
        }
        struct Node *correctBST(struct Node *root) {
           vector<int>v;
           inorder(root,v);
           vector<int>p(v.begin(),v.end());
           sort(p.begin(),p.end());
           int i=0;
           modify(root,p,i);
           return root;
        }
    };
</pre>
