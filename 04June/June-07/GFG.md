## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/least-prime-factor5216/1"> Least Prime Factor </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  vector<int> leastPrimeFactor(int n) {
        vector<int>ans;
        ans.push_back(0);
        ans.push_back(1);
        if(n==1){
            return ans;
        }
        for(int i=2;i<=n;i++){
            for(int j=2;j<=i;j++){
                if(i%j==0){
                    ans.push_back(j);
                    break;
                }
            }
        }
       return ans;
    }
</pre>
