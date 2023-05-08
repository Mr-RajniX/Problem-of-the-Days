## Problem of the Day - [<a href="https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/description/"> 1431. Kids With the Greatest Number of Candies </a>]


#### ⭐<ins>Solution Function Code </ins> -
<pre>

    vector<bool> kidsWithCandies(vector<int>& candies, int extraCandies) {
        int mx = 0;
        for(int i=0; i< candies.size(); i++){
            mx = max(candies[i], mx);
        }
        vector<bool> ans;
        for(int i=0; i< candies.size(); i++){
            int s = candies[i] + extraCandies;
            if( s>= mx ) ans.push_back(true);
            else ans.push_back(false);
        }
        return ans;
    }
</pre>
