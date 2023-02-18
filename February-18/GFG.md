## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/38f100615d0b2efa755e7b07f905e0f8cd2fe5df/1"> Apple Sequences </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int appleSequences(int n, int m, string arr){
        // code here 
        int maxapples=0;
        int oranges=0;
        int start=0;
        int end=0;
        while(end<n)
        {
            if(arr[end]=='O')
                oranges++;
            while(oranges>m)
            {
                if(arr[start]=='O')
                    oranges--;
                start++;
            }
            maxapples=max(maxapples,end-start+1);
            end++;
        }
        return maxapples;
    }
</pre>
