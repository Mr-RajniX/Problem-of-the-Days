## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/c670bf260ea9dce6c5910dedc165aa403f6e951d/1"> Distinct Difference </a>]


#### ⭐<ins>Solution Function Code</ins> -


    vector<int> getDistinctDifference(int N, vector<int> &A) {
        // code here
        set<int>s;
        vector<int>ans(N,0),temp(N,0);
        for(int i=0;i<N;i++){
            temp[i]=s.size();
            s.insert(A[i]);
        }
        s.clear();
        for(int i=N-1;i>=0;i--){
            ans[i]=temp[i]-s.size();
            s.insert(A[i]);
        }
        return ans;
    }
