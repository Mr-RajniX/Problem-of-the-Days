#### Problem of the Day : [1846. Maximum Element After Decreasing and Rearranging](https://leetcode.com/problems/maximum-element-after-decreasing-and-rearranging/)

#### Solution :
<pre>
  int maximumElementAfterDecrementingAndRearranging(vector< int>& arr) {
        sort(arr.begin(),arr.end());
        arr[0] = 1; 
        for (int i = 1; i < arr.size(); ++i) {
            if (abs(arr[i] - arr[i - 1]) <= 1) continue; 
            else arr[i] = arr[i - 1] + 1;
        }
        return arr.back();
    }
</pre>
