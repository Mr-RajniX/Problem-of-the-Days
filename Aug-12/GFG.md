### Problem of the Day : [Longest Increasing Subsequence](https://practice.geeksforgeeks.org/problems/longest-increasing-subsequence-1587115620/1)

#### Solution :
<pre>
  int longestSubsequence(int n, int a[]){
       vector< int >subSeq;
        for(int i=0; i < n ; ++i){
            auto it = lower_bound(subSeq.begin(),subSeq.end(),a[i]);
            if(it != subSeq.end()) *it = a[i];
            else subSeq.push_back(a[i]);
            
        }
        return subSeq.size();
    }
</pre>
