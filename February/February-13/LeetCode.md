## Problem of the Day - [<a href="https://leetcode.com/problems/count-odd-numbers-in-an-interval-range/"> 1523. Count Odd Numbers in an Interval Range </a>]


#### ⭐<ins>Solution Function Code</ins> - Beats 100% Runtime Solutions

      int countOdds(int low, int high) {
        int dist = high - low+1;
        int count = dist/2;
        if(low%2 ==1 && dist%2 == 1)
            return count+1;
        return count;
      }

