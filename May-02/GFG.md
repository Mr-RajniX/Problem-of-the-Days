## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/0a7c7f1089932257071f9fa076f25d353f91e0fd/1"> Cake Distribution Problem </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     bool count(vector<int> &arr,int target,int mid){
          int cnt=0;
          int sum=0;
          for(int i=0;i<arr.size();i++){
              sum+=arr[i];
              if(sum>=mid){
                  cnt++;
                  sum=0;
              }
          }
          if(cnt<target){
              return false;
          }
          return true;
      } 
      int maxSweetness(vector<int>& arr, int n, int k) {
          // Write your code here.
          int low = *min_element(arr.begin(),arr.end());
          int high = 0;
          for(auto x:arr){
              high+=x;
          }
          while(low<=high){
              int mid = low + (high - low)/2;
              if(count(arr,k+1,mid)==false){
                  high = mid - 1;
              }
              else{
                  low = mid + 1;
              }
          }
          return high;
      }

