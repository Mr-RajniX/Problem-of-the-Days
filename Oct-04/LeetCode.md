### Problem of the Day : [706. Design HashMap](https://leetcode.com/problems/design-hashmap/)

#### Solution :
<pre>
    int arr[1000001];
    MyHashMap() {
        fill(arr, arr+1000000, -1);
    }
    
    void put(int key, int value) {
        arr[key] = value;
    }
    
    int get(int key) {
        return arr[key];
    }
    
    void remove(int key) {
        arr[key] = -1;
    }
</pre>
