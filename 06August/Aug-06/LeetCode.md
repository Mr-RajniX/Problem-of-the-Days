### Problem of the Day : [920. Number of Music Playlists](https://leetcode.com/problems/number-of-music-playlists/)

#### Solution : 
<pre>
  const int MOD = 1e9 + 7;

    int numMusicPlaylists(int n, int goal, int k){
        vector< vector < long > > dp(goal + 1, vector< long > (n + 1, 0) );
        dp[0][0] = 1;
        for (int len = 1; len <= goal; len++){
            for (int uniq = 1; uniq <= min(len, n); uniq++) {
                long addNewSong = (dp[len - 1][uniq - 1] *(n - (uniq - 1))) % MOD;
                long replayOldSong = 0;
                if (uniq > k)
                    replayOldSong = (dp[len - 1][uniq] *(uniq - k)) % MOD;
                dp[len][uniq] = (addNewSong + replayOldSong) % MOD;
            }
        }
        return dp[goal][n];
    }
</pre>
