## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/rearrange-an-array-with-o1-extra-space3142/1"> Rearrange an array with O(1) extra space </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  void arrange(long long arr[], int n) {
        int i;
        long long maax=n; 
        for(i=0; i < n;i++){
            arr[i] = arr[i]+(arr[arr[i]] % maax) * maax;
        }
        for(i=0; i < n;i++){
            arr[i] /= maax;
        }
    }
</pre>
