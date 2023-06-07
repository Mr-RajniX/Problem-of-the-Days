## Problem of the Day - [<a href="https://leetcode.com/problems/minimum-flips-to-make-a-or-b-equal-to-c/"> 1318. Minimum Flips to Make a OR b Equal to c </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int minFlips(int a, int b, int c) {
        int ans=0;
        while(a||b||c){
            int x1=a&1;
            int x2=b&1;
            int x3=c&1;
            if((x1|x2)!=x3){
                if(x1&x2)   ans+=2;
                else ans+=1;
            }
            a=a>>1;
            b=b>>1;
            c=c>>1;
        }
        return ans;
    }
</pre>
