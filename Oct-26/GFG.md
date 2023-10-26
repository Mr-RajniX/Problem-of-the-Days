#### Problem of the Day : [Minimum Operations](https://practice.geeksforgeeks.org/problems/find-optimum-operation4504/1)

#### Solution :
<pre>
  int minOperation(int n){
        int ans=1;
        while(n/2){
            if(n%2)
                ans += 2;
            else
                ans++;
            n /= 2;
        }
        return ans;
    }
</pre>
