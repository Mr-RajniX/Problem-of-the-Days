## Problem of the Day - [<a href="https://leetcode.com/problems/find-smallest-letter-greater-than-target/"> 744. Find Smallest Letter Greater Than Target </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  char nextGreatestLetter(vector<char>& letters, char target) {
        int left = 0;
        int right = letters.size() - 1;
        int mid;
        while (left <= right) {
            mid = (left + right) / 2;
            if (letters[mid] <= target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return left == letters.size() ? letters[0] : letters[left];
    }
</pre>
