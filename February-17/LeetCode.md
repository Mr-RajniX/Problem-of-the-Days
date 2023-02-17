## Problem of the Day - [<a href="https://leetcode.com/problems/minimum-distance-between-bst-nodes/description/"> 783. Minimum Distance Between BST Nodes </a>]


#### ⭐<ins>Solution Function Code</ins> -


          void inorder(TreeNode* root,vector<int>&v){
                  if(root==NULL)return ;
                  inorder(root->left,v);
                  v.push_back(root->val);
                  inorder(root->right,v);
          }
        public:
          int minDiffInBST(TreeNode* root) {
                vector<int>res;
                inorder(root,res);
                sort(res.begin(),res.end());
                int n =res.size();
                int mini=INT_MAX;
                for(int i=1;i<n;++i){
                      int diff=res[i]-res[i-1];
                      mini=min(mini,diff);
                }
                return mini;
          }

