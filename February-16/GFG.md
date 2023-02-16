## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/e2d156755ca4e0a9b9abf5680191d4b06e52b1a8/1"> Good Stones </a>]


#### ⭐<ins>Solution Function Code</ins> -

    int goodStones(int n,vector<int> &arr){
        // Code here
        vector<int> dp(n,0);
         for(int i=0;i<n;i++){
            if(dp[i] == 0){
                int temp=i;
                bool good = false;
                while(dp[temp] != 1){
                    if(arr[temp] == 0) break;
                    dp[temp] = 1;
                    temp += arr[temp];
                    if(temp<0 || temp>=n || dp[temp] == 2){
                        good = true;
                        break;
                    }
                }
                if(good){
                    temp = i;
                    while(temp>=0 && temp<n){
                        dp[temp] = 2;
                        temp += arr[temp];
                    }
                }
            }
        }
        int ans=0;
        for(int i=0;i<n;i++){
            if(dp[i] == 2){
                ans++;
            }
        }
        return ans;
    }
