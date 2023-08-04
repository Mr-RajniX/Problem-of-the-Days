### Problem of the Day : [Delete middle element of a stack](https://practice.geeksforgeeks.org/problems/delete-middle-element-of-a-stack/1)

####[Approach]
<pre>
  void deleteMid(stack<int>&s, int n){
        if(n%2==0){
          int target=(n/2)-1;
          s.remove(t);
        }else{
          int target=n/2;
          s.remove(t);
        }
    }
</pre>
#### Solution :
<pre>
    void deleteMid(stack< int >&s, int n){
      stack< int >st;
      int l=n/2;
      while(l--){
          st.push(s.top());
          s.pop();
      }
      s.pop();
      while(!st.empty()){
          s.push(st.top());
          st.pop();
      }
    }
</pre>
