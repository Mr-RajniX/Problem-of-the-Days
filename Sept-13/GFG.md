### Problem of the Day : [Largest number possible](https://practice.geeksforgeeks.org/problems/largest-number-possible5028/1)

#### Solution :
<pre>
  string findLargest(int N, int S){
        if(S > (9*N)) return "-1";
        if( S == 0 && N > 1) return "-1";
        
        int nines = S/9;
        int rem = S%9;
        string ans(nines, '9');
        if( rem != 0) ans += to_string(rem);
        if(ans.length() == N) return ans;
        else{
            string zeroes(N - ans.length(), '0');
            ans += zeroes;
            return ans;
        }
    }
</pre>
