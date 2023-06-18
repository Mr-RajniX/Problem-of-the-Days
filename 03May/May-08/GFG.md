## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/7488b7721e8aa5e5fc37d56af8b9c89e329c796f/1"> Binary Modulo </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int modulo(string s,int m)
        {
            //code here
            long long int k=0 ;
            long long int p=1 ;
            int n = s.size()   ;
            for (int j=n-1;j>=0;j--)
            {
                 k=(k+(s[j]-'0')*p)%m ; 
                 p=(p*2)%m ;
            } 
            int r=k%m ;
            return(r);
        }
</pre>
