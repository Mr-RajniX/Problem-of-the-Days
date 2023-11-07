#### Problem of the Day : [Check whether K-th bit is set or not](https://practice.geeksforgeeks.org/problems/check-whether-k-th-bit-is-set-or-not-1587115620/1)

#### Solution :
<pre>
  bool checkKthBit(int n, int k){
        return (n=n>>k)%2!=0;
    }
</pre>
