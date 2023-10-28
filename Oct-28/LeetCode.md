#### Problem of the Day : [1220. Count Vowels Permutation](https://leetcode.com/problems/count-vowels-permutation/)

#### Solution :
<pre>
  int countVowelPermutation(int n) {
        const int MOD = 1000000007;
        long countA = 1, countE = 1, countI = 1, countO = 1, countU = 1;

        for (int length = 1; length < n; length++) {
            long nextCountA = countE;
            long nextCountE = (countA + countI) % MOD;
            long nextCountI = (countA + countE + countO + countU) % MOD;
            long nextCountO = (countI + countU) % MOD;
            long nextCountU = countA;
            countA = nextCountA;
            countE = nextCountE;
            countI = nextCountI;
            countO = nextCountO;
            countU = nextCountU;
        }
        long totalCount = (countA + countE + countI + countO + countU) % MOD;
        return static_cast< int>(totalCount);
    }
</pre>
