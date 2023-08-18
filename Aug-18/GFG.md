### Problem of tha day : [Leaders in an array](https://practice.geeksforgeeks.org/problems/leaders-in-an-array-1587115620/1)

#### Solution :
<pre>
  vector < int > leaders(int a[], int n){
        vector < int > result;
        int maxRight = a[n - 1];
        result.push_back(maxRight);
        for (int i = n - 2; i >= 0; i--) {
            if (a[i] >= maxRight) {
                maxRight = a[i];
                result.push_back(maxRight);
            }
        }
        reverse(result.begin(), result.end());
        return result;
    }
</pre>
