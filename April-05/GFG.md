## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/3d49e4cce2820a813da02d1587c2dd9c542ce769/1"> Count Special Numbers </a>]


#### ⭐<ins>Solution Function Code #1</ins> -


    int countSpecialNumbers(int N, vector<int> arr) {
        int maxi=*max_element(arr.begin(),arr.end());
        unordered_map<int,int> mp;
        int count=0;
        for(int i=0;i<N;i++){
            int ele=arr[i];
            if(mp[ele]<2) {
                for(int j=ele;j<=maxi;j+=ele)
                {
                    mp[j]++;
                }
            }
        }        
        for(int i=0;i<N;i++){
            int ele=arr[i];
            if(mp[ele]>1) count++;
        }
        return count;
    }

