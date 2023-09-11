### Problem of the Day : [Lucky Numbers](https://practice.geeksforgeeks.org/problems/lucky-numbers2911/1)

#### Solution :
<pre>
  bool isLucky(int n) {
        for(int i = 2; i <= n; i++){
            if(n%i == 0) return false;
            n = n - (n/i);
        }return true;
    }
</pre>
