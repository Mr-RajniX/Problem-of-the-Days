## Problem of the Day - [<a href="https://leetcode.com/problems/kth-largest-element-in-a-stream/"> 703. Kth Largest Element in a Stream </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  int k;
    priority_queue<int, vector<int>, greater<int>> pq;
    KthLargest(int k, vector<int>& nums): k(k){
        for(int x: nums) {
            pq.push(x);
            if (pq.size()> k) pq.pop();
        }
    }    
    int add(int val) {
        pq.push(val);
        if (pq.size()> k) pq.pop();   
        return pq.top();      
    }
</pre>
