## Problem of the Day - [<a href="https://leetcode.com/problems/can-make-arithmetic-progression-from-sequence/"> 1502. Can Make Arithmetic Progression From Sequence </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  bool canMakeArithmeticProgression(vector<int>& arr) {
        int n = arr.size();
        sort(arr.begin(), arr.end());
        int diff = arr[1] - arr[0];
        for(int i = 2; i < n; i++){
            if((arr[i] - arr[i - 1]) != diff){
                return false;
            }
        }
        return true;
    }
</pre>
