## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/arithmetic-number2815/1"> Arithmetic Number </a>]


#### ⭐<ins>Solution Function Code</ins> -


    int inSequence(int A, int B, int C){
        // code here
        if(C==0 && A==B) return 1;
        double n = (double) (B-A)/C + 1;
        // cout << n << endl;
        if(n != int(n)) return 0;
        if(n>0) return 1;
        return 0;
    }
