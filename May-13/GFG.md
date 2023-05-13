## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/ed0422e992899f3f46340ce97b0090683ceebd67/1"> Bit Magic </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int bitMagic(int n, vector<int> &arr) {
        // code here
        int count=0;
        for(int i=0; i<(int)(ceil(n/2.0)); i++){
            if(arr[i]!=arr[n-1-i]){
                count++;
            }
        }
        return (int)(ceil(count/2.0));
    }
</pre>
