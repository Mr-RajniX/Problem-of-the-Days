## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/1f05c7c12b1084f270c57566b2110967c046730d/1"> Make Array Elements Equal </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    long long int minOperations(int N) {
        long long ans=0;
        if(N%2==0){
            ans=(N/2)*1ll*(N/2);
        }
        else{
            ans=(N/2)*1ll*((N/2)+1);
        }
        return ans;
    }
</pre>
