## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/ticket-counter-2731/1"> Ticket Counter </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int distributeTicket(int N, int K) {
        int i=1; int j=N; 
        
        while(i<=j){
            if(j-i+1>K)
                i+=K;
            else
              return j;  
            
            if(j-i+1>K)
                j-=K;
            else
                 return i;
        }
    }
</pre>
