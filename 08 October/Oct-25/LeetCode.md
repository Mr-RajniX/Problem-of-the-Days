#### Problem of the Day : [779. K-th Symbol in Grammar](https://leetcode.com/problems/k-th-symbol-in-grammar/)

#### Solution :
<pre>
  int kthGrammar(int n, int k) {
        bool value = true;
        n = pow(2 , n);
        while(n != 1){
            n /= 2;
            if(k > n){
                k -= n;
                value = !value;
            }
        }return (value ? 0 : 1);
    }
</pre>
