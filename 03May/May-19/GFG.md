## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/find-k-th-smallest-element-in-given-n-ranges/1"> Find k-th smallest element in given n ranges </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     vector<int>kthSmallestNum(int n, vector<vector<int>>&range, int q, vector<int>queries){        
          sort(range.begin(),range.end());
          vector<int> res(q,-1);
          for(int i=0;i<q;i++){

              int prev = 0;
              int k = queries[i];
              for(auto it : range){

                  int l = it[0];
                  int r = it[1];

                  if(k<=r- max(l,prev)+1 ){
                      res[i] =  max(l,prev)+k-1;
                      break;
                  } 
                  k -= r- max(l,prev)+1;
                  prev = r+1;
              }

          }
          return res;
      }
</pre>
