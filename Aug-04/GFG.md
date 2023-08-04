### Problem of the Day : [Reverse a Stack](https://practice.geeksforgeeks.org/problems/reverse-a-stack/1)

#### Solution :
<pre>
  void Reverse(stack< int > &st){
        stack< int >s;
        while(!st.empty()){
            s.push(st.top());
            st.pop();
        }
        st=s;
    }
</pre>
