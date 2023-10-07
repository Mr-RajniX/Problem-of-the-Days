### Problem of the Day : [Rotate Bits](https://practice.geeksforgeeks.org/problems/rotate-bits4524/1)

#### Solution :
<pre>
  vector< int> rotate (int n, int d){
            d %= 16;
            int L = ((n << d) | (n >> (16-d))) & 65535;
            int R = ((n >> d) | (n << (16-d))) & 65535;
            return {L,R};
        }
</pre>
