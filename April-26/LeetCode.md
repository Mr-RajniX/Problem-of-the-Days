## Problem of the Day - [<a href="https://leetcode.com/problems/add-digits/"> 258. Add Digits </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int addDigits(int num) {
        int n = 0;
        while(num){
            n += (num%10);
            num /= 10;
        }        
        if(n < 10)
            return n;
        else
            return addDigits(n);
    }
</pre>
