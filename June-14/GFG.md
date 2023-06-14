## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/chinky-and-diamonds3340/1"> Maximum Diamonds </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  long long maxDiamonds(int A[], int N, int K) {
        priority_queue<long long int> q;
        long long int cnt = 0;
        for( int i = 0; i< N; i++) {
            q.push(A[i]);
        }
        while( K--) {
            long long int t = q.top();
            cnt += q.top();
            q.pop();
            q.push(t/2);
        }
        return cnt;
    }
</pre>
