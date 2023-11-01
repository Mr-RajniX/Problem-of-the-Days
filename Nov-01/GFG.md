#### Problem of the Day : [Frequencies of Limited Range Array Elements](https://www.geeksforgeeks.org/problems/frequency-of-array-elements-1587115620/1)

#### Solution :
<pre>
  void frequencyCount(vector<int >& arr,int N, int P){ 
        int mod=1+max(N,P);
        for(int idx:arr)if(idx%mod-1 < N)arr[idx%mod-1]+=mod;
        for(int &i:arr)i/=mod;
    }
</pre>
