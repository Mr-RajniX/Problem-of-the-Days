## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/aa8c89caad6b5c3a76ba5e6d65454f77aac3f3543526/1"> Remainder on dividing by 11 </a>]


#### ⭐<ins>Solution Function Code</ins> -


    int xmod11(string x){
       long long ans=0;
        for(int i=0;i<x.length();i++)
            ans=(ans * 10+x[i]-'0')%11;
        return ans;
    }

