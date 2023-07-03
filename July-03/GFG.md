## problem of the day : <a href="https://practice.geeksforgeeks.org/problems/maximum-index3307/1"> Maximum Index </a>

### Solution:
<pre>
  int maxIndexDiff(int arr[], int n) {
        // code here
        vector< int > leftMin(n),rightMax(n);

        leftMin[0] = arr[0];
        for (int i = 1; i < n; i++) {
            leftMin[i] = min(arr[i], leftMin[i-1]);
        }

        rightMax[n-1] = arr[n-1];
        for (int i = n-2; i >= 0; i--) {
            rightMax[i] = max(arr[i], rightMax[i+1]);
        }

        int i = 0, j = 0;
        int result = -1;
        while (i < n && j < n) {
            if (leftMin[i] <= rightMax[j]) {
                result = max(result, j - i);
                j++;
            } else {
                i++;
            }
        }

        return result;
    }
</pre>
