## Problem of the Day - [<a href="https://leetcode.com/problems/find-the-highest-altitude/"> 1732. Find the Highest Altitude </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int largestAltitude(vector<int>& gain) {
        int maxAlt = 0;
        int currentAlt = 0;
        
        for (int i = 0; i < gain.size(); i++) {
            currentAlt += gain[i];
            maxAlt = max(maxAlt, currentAlt);
        }
        return maxAlt;
    }
</pre>
