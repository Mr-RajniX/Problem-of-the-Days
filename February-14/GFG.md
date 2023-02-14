## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/51b266505221b97522b1d2c86ddad1868a54831b/1"> Walls Coloring </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int minCost(vector<vector<int>> &colors, int N) {
        // Write your code here.
        int Ai_1 = colors[0][0], Bi_1 = colors[0][1], Ci_1 = colors[0][2];
        for(int i = 1; i< N; i++){
            int t1 = colors[i][0] + min(Bi_1, Ci_1);
            int t2 = colors[i][1] + min(Ai_1, Ci_1);
            int t3 = colors[i][2] + min(Bi_1, Ai_1);
            Ai_1 = t1, Bi_1 = t2, Ci_1 = t3;
        }
        return min(Ai_1, min(Bi_1, Ci_1));
    }
</pre>
