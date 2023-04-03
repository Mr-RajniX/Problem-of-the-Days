## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/0960a833f70b09c59444ea487f99729929fc8910/1"> Number of Subarrays of 0's </a>]


#### ⭐<ins>Solution Function Code</ins> -

    long long int no_of_subarrays(int n, vector<int> &arr) {
        long long int count=0;
        long long int len=0;
        for(int i=0; i<n; i++){
            if(arr[i]==0)
                len++;
            else{
                count+= (len*(len+1)/2);
                len=0;
                } 
        }
        count+= (len*(len+1)/2);
        return count;
    }

