## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/35bff0ee40090b092e97b02f649085bf1390cc67/1"> Find Number </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   long long findNumber(long long n){
        // Code here
        long long ans = 0;
        vector<int> vec;
        while(n > 0) {
            n--, vec.push_back(n%5);
            n /= 5;
        }
        for(int i = vec.size()-1; i >= 0; i--) {
            ans = ans*10 + 2*vec[i] + 1;
        }
        return ans;
    }
</pre>
