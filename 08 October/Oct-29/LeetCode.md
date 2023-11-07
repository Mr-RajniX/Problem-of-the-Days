#### Problem of the Day : [458. Poor Pigs](https://leetcode.com/problems/poor-pigs/)

#### Solution :
<pre>
  int poorPigs(int buckets, int minutesToDie, int minutesToTest) {
        return ceil(log2(buckets)/log2(int(minutesToTest/minutesToDie)+1));
    }
</pre>
