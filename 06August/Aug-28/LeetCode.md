### Problem of the Day : [225. Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues/)

#### Solution :
<pre>
  queue < int > q;
    MyStack() {}    
    void push(int x) {
        q.push(x);
        for (int i = 0; i < q.size() - 1; ++i) {
            q.push(q.front());
            q.pop();
        }
    }
    
    int pop() {
        int val = q.front();
        q.pop();
        return val;
    }
    
    int top() {
        return q.front();
    }
    
    bool empty() {
        return q.empty();
    }
</pre>
