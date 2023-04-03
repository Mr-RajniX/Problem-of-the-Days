## Problem of the Day - [<a href="https://leetcode.com/problems/boats-to-save-people/description/"> 881. Boats to Save People </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    int numRescueBoats(vector<int>& people, int limit) {
        sort(people.begin(), people.end());
        int count =0;
        int start = 0, end = people.size()-1;
        while(start<=end){
            if(people[start] + people[end] <= limit){
                start++; end--;
            }else end--;
            count++;
        }
        return count;
    }
</pre>
