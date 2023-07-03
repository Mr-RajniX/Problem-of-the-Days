## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/queue-operations/1"> Queue Operations </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

    void insert(queue<int> &q, int k){
        q.push(k);
    }
    int findFrequency(queue<int> &q, int k){
        queue<int>p=q;
        int count=0;
        while(!p.empty()){
            if(p.front()==k){
                count++;
            }
            p.pop();
        }
        if(count==0){
            return -1;
        }
        return count;
    }
</pre>
