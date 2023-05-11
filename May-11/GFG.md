## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/32dc957908c2eb8beeeaeedf81f37df20d37c308/1"> Palindrome with minimum sum </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


     int minimumSum(string s) {
          int n=s.size();
          int i=0,j=n-1;
          while(i<j){
              if(s[i]!='?' and s[j]!='?' and s[i]!=s[j]){
                  return -1;
              }
              else if(s[i]=='?' and s[j]!='?'){
                  s[i]=s[j];
              }
              else if(s[i]!='?' and s[j]=='?'){
                  s[j]=s[i];
              }
              else if(i!=0 and s[i]=='?' and s[j]=='?' and s[i-1]!='?'){
                  s[i]=s[j]=s[i-1];
              }
              i++;
              j--;
          }
          int ans=0;
          for(int i=1;i<=n/2;i++){
              if(s[i]=='?'){
                  continue;
              }
              if(s[i-1]!='?'){
                  ans+=(2*abs(s[i]-s[i-1]));
              }
          }
          return ans;
      }
