### Problem of the Day : [First and last occurrences of x](https://practice.geeksforgeeks.org/problems/first-and-last-occurrences-of-x3116/1)

#### Solution :
<pre>
  vector<int> find(int arr[], int n , int x ){
        int first = -1, last = -1;
        for (int i = 0; i < n; i++) {
            if (x != arr[i])
                continue;
            if (first == -1)
                first = i;
            last = i;
        } return { first, last};
    }
</pre>
