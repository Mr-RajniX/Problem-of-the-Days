## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/a6528c893d4ab645ec6e0690c7982748385099c8/1"> Update Queries </a>]


#### ⭐<ins>Solution Function Code</ins> -


    vector<int> updateQuery(int n,int q,vector<vector<int>> &u){
            // code here
            vector<vector<int>> bit(32,vector<int>(n+1,0));
            for(int i=0;i<q;i++){
                int l=u[i][0],r=u[i][1],x=u[i][2];
                l--;r--;
                for(int j=0;j<32;j++){
                    if(x&(1<<j)){
                        bit[j][l]++;
                        bit[j][r+1]--;
                    }
                }
            }
            for(int j=0;j<32;j++){
                for(int i=1;i<n;i++){
                    bit[j][i]+=bit[j][i-1];
                }
            }            
            vector<int> fans(n);
            for(int j=0;j<32;j++){
                for(int i=0;i<n;i++){
                    if(bit[j][i]!=0){
                        fans[i]|=(1<<j);        
                    }
                }
            }            
            return fans;
    }

