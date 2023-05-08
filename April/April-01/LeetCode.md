## Problem of the Day - [<a href="https://leetcode.com/problems/binary-search/description/"> 704. Binary Search </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    int search(vector<int>& nums, int target) {
        int s = 0, e = nums.size()-1;
        while(s<=e){
            int mid = s + (e-s) / 2 ;
            if(nums[mid]==target) return mid;
            else if(nums[mid] > target) e = mid-1;
            else s=mid+1;
        }
        return -1;
    }
</pre>
#### ⭐<ins>Solution Function Code #2</ins> -
<pre>

    int search(vector<int>& n, int t) {
        int ind = lower_bound(n.begin(),n.end() , t) - n.begin();
        if(ind < n.size() && n[ind]==t ) return ind;
        return -1;
    }
</pre>
