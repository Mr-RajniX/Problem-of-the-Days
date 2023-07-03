## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/-matchsticks-game4906/1"> Matchsticks game </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int matchGame(long long N) {
        int ans = N % 5;
        return (ans == 0) ? -1 : ans;
    }
</pre>
