#### Problem of the Day : [2849. Determine if a Cell Is Reachable at a Given Time](https://leetcode.com/problems/determine-if-a-cell-is-reachable-at-a-given-time/)

#### Solution :
<pre>
  bool isReachableAtTime(int sx, int sy, int fx, int fy, int t) {
        int d=Chebyshev(sx, sy, fx, fy);
        return d>0 ? t>=d: t!=1;
    }
    int Chebyshev(int sx, int sy, int fx, int fy){
        return max(abs(sx-fx), abs(sy-fy) );
    }
</pre>
