### Problem of the Day : [Find first set bit](https://practice.geeksforgeeks.org/problems/find-first-set-bit-1587115620/1)

#### Solution :
<pre>
  unsigned int getFirstSetBit(int n){
        unsigned int count = 0;
        while(n){
            count++; 
            if (n & 1) return count;
            n = n >> 1;
        }return count;
    }
</pre>
