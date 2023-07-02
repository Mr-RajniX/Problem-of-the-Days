## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/copy-set-bits-in-range0623/1"> Copy Set Bits in Range </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>
  int setSetBit(int x, int y, int l, int r){
        int mx=x;
        for(int i=0;i < l-1;i++){
            mx=mx/2;
            y=y/2;
        }
        for(int i=l-1;i <= r-1;i++){
            int modx=mx%2;
            int mody=y%2;
            if(mody==1&&modx==0){
                x=x+pow(2,i);
            }
            mx=mx/2;
            y=y/2;
        }
        return x;
    }
</pre>
