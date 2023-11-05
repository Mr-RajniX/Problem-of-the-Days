#### Problem of the Day : [1535. Find the Winner of an Array Game](https://leetcode.com/problems/find-the-winner-of-an-array-game/)

#### Solution :
<pre>
  int getWinner(vector< int>& arr, int k) {
        int currentWinner = arr[0];
        int count = 0;
        for (int i = 1; i < arr.size(); i++) {
            if (arr[i] > currentWinner) {
                currentWinner = arr[i];
                count = 1;
            } else {
                count++;
            }
            if (count == k) {
                return currentWinner;
            }
        }
        return currentWinner;
    }
</pre>
