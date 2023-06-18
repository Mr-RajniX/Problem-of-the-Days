## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/2145720aebf8ea0b07f76b17217b3353a0fbea7f/1"> Fill the Matrix </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int minIteration(int n, int m, int x, int y){    
        // code here
        int firstcorner=x-1+y-1;
        int secondcorner=x-1+m-y;
        int thirdcorner=n-x+y-1;
        int fourthcorner=n-x+m-y;
        return max(max(firstcorner,secondcorner),max(thirdcorner,fourthcorner));
    }
</pre>
