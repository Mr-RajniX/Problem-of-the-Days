### Problem of the Day : [215. Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/)

#### Solution :
<pre>
    int findKthLargest(vector< int >& nums, int k) {
        priority_queue < int,vector < int > ,greater < int > > p;
        for(auto x:nums){
            p.push(x);
            if(p.size() > k) p.pop();
        }
        return p.top();
    }</pre>
