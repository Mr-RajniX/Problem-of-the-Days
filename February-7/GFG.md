## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/4dfa8ba14d4c94f4d7637b6b5246782412f3aeb8/1"> Length of the longest subarray with positive product </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int maxLength(vector<int> &arr,int n){
           //code here
           
           int posLen = 0, negLen = 0, maxLen = 0;
           
           for (int i : arr) {
               if (i == 0) 
                    posLen = 0, negLen = 0;
               else {
                   if (i < 0) swap(posLen, negLen);
                   if (posLen > 0 || i > 0) ++posLen;
                   if (negLen > 0 || i < 0) ++negLen;
                   maxLen = max(maxLen, posLen);
                }
            }
            return maxLen;
        }
</pre>
