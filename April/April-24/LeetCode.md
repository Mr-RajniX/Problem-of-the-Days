## Problem of the Day - [<a href="https://leetcode.com/problems/last-stone-weight/"> 1046. Last Stone Weight </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   int lastStoneWeight(vector<int>& a) {
        priority_queue<int>pq(a.begin(),a.end());
        while(pq.size() > 1){
            int a = pq.top();
            pq.pop();
            int b = pq.top();
            pq.pop();
            if(a != b)
                pq.push(abs(a-b));
        }
        return pq.empty() ? 0 : pq.top();
    }
</pre>
