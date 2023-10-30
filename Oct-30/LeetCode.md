#### Problem of the Day : [1356. Sort Integers by The Number of 1 Bits](https://leetcode.com/problems/sort-integers-by-the-number-of-1-bits/)

#### Solution :
<pre>
    vector< int> sortByBits(vector< int>& arr) {
        sort(arr.begin(), arr.end(), compare);
        return arr;
    }

    static bool compare(int a, int b) {
        int bitCountA = countBits(a);
        int bitCountB = countBits(b);
        if (bitCountA == bitCountB) {
            return a < b; 
        }return bitCountA < bitCountB; 
    }

    static int countBits(int num) {
        int count = 0;
        while (num > 0) {
            count++;
            num &= (num - 1); 
        }        
        return count;
    }
</pre>
