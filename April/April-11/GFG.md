## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/84963d7b5b84aa24f7807d86e672d0f97f41a4b5/1"> Maximum Length </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>
    int solve(int a, int b, int c) {
        // code here
        int n = max(a,max(b,c));
        if(n <= (2*(a+b+c-n+1))) return a+b+c;
        return -1;
    }
</pre>
