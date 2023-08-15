# Happy Independence Day <img src="https://em-content.zobj.net/thumbs/72/google/350/flag-india_1f1ee-1f1f3.png" width=40>
### Problem of the Day : [Flip Bits](https://practice.geeksforgeeks.org/problems/flip-bits0240/1)

#### Solution : 
<pre>
  int maxOnes(int a[], int n){
        int ans = 0, flips = 0;
        for(int i = 0; i < n; i++){
            if(a[i] == 0) flips++;
            else flips--;
            ans = max(ans, flips);
            if(flips < 0) flips = 0;
        }
        int ones = 0;
        for(int i = 0; i < n; i++){
            if(a[i] == 1) ones++;
        }
        return ones+ans;
    }
</pre>
