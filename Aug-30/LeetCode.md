### Problem of the day : [2366. Minimum Replacements to Sort the Array](https://leetcode.com/problems/minimum-replacements-to-sort-the-array/)

#### Solution :
<pre>
    long long minimumReplacement(std::vector < int > & nums) {
        long long operations = 0;
        long long prev_bound = nums.back();
        
        for (auto it = nums.rbegin() + 1; it != nums.rend(); ++it) {
            long long num = *it;
            long long no_of_times = (num + prev_bound - 1) / prev_bound;
            operations += no_of_times - 1;
            prev_bound = num / no_of_times;
        }
        
        return operations;
    }
};
</pre>
