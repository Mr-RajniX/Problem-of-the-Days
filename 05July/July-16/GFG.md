### Problem of the Day : [Queue Reversal](https://practice.geeksforgeeks.org/problems/queue-reversal/1)

#### Solution :
<pre>
  queue< int > rev(queue< int > q){
        vector< int >s;
        while (!q.empty()){
            s.push_back(q.front());
            q.pop();
        }    
        reverse(s.begin(), s.end());
        for(int x : s){
            q.push(x);
        }return q;
    }
</pre>
