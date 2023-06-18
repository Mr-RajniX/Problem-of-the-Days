## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/5bfe93cc7f5a214bc6342709c78bc3dceba0f1c1/1"> Maximum Identical Bowls </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int getMaximum(int N, vector<int> &arr) {
        if(N == 1)
            return 1;
        long long sum = 0;
        for(auto elem: arr)
            sum += elem;
        while(N != 0 && sum % N-- != 0);
        return N + 1;
    }
</pre>
