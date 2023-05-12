## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/3a93b6a25a7b88e4c80a1fee00898fd8022eb108/1"> Array Operations </a>]


#### ⭐<ins>Solution Function Code #1</ins> -

     int arrayOperations(int n, vector<int> &arr) {
          // code here
          int ans=1;
          bool check=false;
          for(int i=0;i<n-1;i++){
              if(arr[i]==0){                 
                  check=true;
              }
              if(arr[i]!=0 and arr[i+1]==0){
                  ans++;
                  check=true;
              }
          }
          if(check==false) return -1;
          if(arr[n-1]==0) return ans-1;
          return ans;
      }

