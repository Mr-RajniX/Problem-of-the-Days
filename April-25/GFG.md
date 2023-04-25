## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/cec5db442a5652d07dd41e37ea780345f08c9a3d/1"> Game Of Subsets </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int goodSubsets(vector<int> &arr, int n){
    // Code here
    long long mod = 1e9 + 7;
    vector<int> cnt(31, 0);
    int primes[10] = {2, 3, 5, 7, 11, 13, 17, 19, 23, 29};
    int maskSize = 1<<10;
    for(int x : arr) cnt[x]++;
    long long dp[31][maskSize]; 
    dp[0][0] = 1; 
    for(int j = 1; j < maskSize; j++) dp[0][j] = 0; 
    for(int i = 1; i <= 30; i++) {
        int mask = 0;
        bool canBeUsed = true;
        for(int j = 0; j < 10; j++) {
            int p = primes[j];
            if(i%p == 0 && i%(p*p) == 0) {
                canBeUsed = false;
                break; 
            }
            if(i%p == 0) mask |= (1 << j);
        }
        for(int j = 0; j < maskSize; j++) {
            long long subsets = dp[i-1][j];
            if(canBeUsed && (j&mask) == mask) subsets = (subsets + (cnt[i] * dp[i-1][j&(~mask)]) % mod) % mod;
            dp[i][j] = subsets;
        }
    }
    long long ans = 0;
    for(int mask = 1; mask < maskSize; mask++) ans = (ans + dp[30][mask]) % mod;
    return ans;
}
</pre>
