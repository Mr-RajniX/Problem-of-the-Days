## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/lemonade-change/1"> Lemonade Change </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  bool lemonadeChange(int N, vector<int> &bills) {
        // code here
        int f=0,t=0,tw=0;
        for(int i=0;i < N;i++){
            int k=bills[i];
            k-=5;
            if(k==0)
                f++;
            else if(k==5){
                if(f==0)
                    return false;
                else{
                    f--;
                    t++;
                }
            }
            else if(k==15){
                if(t>0){
                    k-=10;
                    t--;
                }
                while(k>0 and f>0){
                    k-=5;
                    f--;
                }
                if(k>0)
                    return false;
            }
        }
        return true;
    }
</pre>
