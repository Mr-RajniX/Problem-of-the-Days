#### Problem of the Day : [1095. Find in Mountain Array](https://leetcode.com/problems/find-in-mountain-array/)

#### Solution :
<pre>
  int findInMountainArray(int target, MountainArray &mountainArr) {
        int length = mountainArr.length();
        int peakIndex = findPeakIndex(1, length - 2, mountainArr);
        int increasingIndex = binarySearch(0, peakIndex, target, mountainArr, false);
        if (mountainArr.get(increasingIndex) == target) 
            return increasingIndex; 

        int decreasingIndex = binarySearch(peakIndex + 1, length - 1, target, mountainArr, true);
        if (mountainArr.get(decreasingIndex) == target) 
            return decreasingIndex; 
        return -1; 
    }

    int findPeakIndex(int low, int high, MountainArray &mountainArr) {
        while (low != high) {
            int mid = low + (high - low) / 2;
            if (mountainArr.get(mid) < mountainArr.get(mid + 1)) {
                low = mid + 1; 
            } else {
                high = mid; 
            }
        }
        return low; 
    }

    int binarySearch(int low, int high, int target, MountainArray &mountainArr, bool reversed) {
        while (low != high) {
            int mid = low + (high - low) / 2;
            if (reversed) {
                if (mountainArr.get(mid) > target)
                    low = mid + 1;
                else
                    high = mid; 
            } else {
                if (mountainArr.get(mid) < target)
                    low = mid + 1; 
                else
                    high = mid; 
            }
        }
        return low; 
    }
</pre>
