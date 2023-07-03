## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/next-happy-number4538/1"> Next Happy Number </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  bool solve(int n){
        if(n==1 || n==7)return true;
        if(n==2 || n==4 || n==8 || n==3 || n==9 || n==5 || n==6)return false;
        int sq_sum=0;
        while(n){
            int x=n%10;
            sq_sum+=(x*x);
            n/=10;
        }
        return solve(sq_sum);
    }
    int nextHappy(int n){
        while(true){
            n++;
            if(solve(n))return n;
        }
        return 0;
    }
</pre>
