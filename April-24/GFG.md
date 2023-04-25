## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/a520c08a8ea9b617be25c38b0fc2fe057e889253/1"> Nearest smaller tower </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   vector<int> nearestSmallerTower(vector<int> arr)
    {
        // code here
vector<int> left(arr.size());
        stack<int> st1;
        for(int i=0;i<arr.size();i++)
        {
            while(st1.size() && arr[st1.top()]>=arr[i])
                st1.pop();
            if(st1.size())
               left[i]=st1.top();
            else
               left[i]=-1;
            st1.push(i);   
        }
        // On-right
        vector<int> right(arr.size());
        stack<int> st2;
        for(int i=arr.size()-1;i>=0;i--)
        {
            while(st2.size() && arr[st2.top()]>=arr[i])
                st2.pop();
            if(st2.size())
               right[i]=st2.top();
            else
               right[i]=-1; 
            st2.push(i);   
        }
        //final
        vector<int> ans(arr.size());
        for(int i=0;i<arr.size();i++)
        {
            if(left[i]==-1 and right[i]==-1)
                ans[i]=-1;
            else if(left[i]==-1)
                ans[i]=right[i];
            else if(right[i]==-1)
                ans[i]=left[i];
            else
            {
                if( abs(i-left[i]) < abs(i-right[i]) )
                    ans[i]=left[i];
                else if( abs(i-left[i]) > abs(i-right[i]) )
                    ans[i]=right[i];  
                else if(arr[left[i]] < arr[right[i]])
                    ans[i]=left[i];
                else if(arr[left[i]] > arr[right[i]])
                    ans[i]=right[i];  
                else   
                    ans[i]=min(left[i],right[i]);     
            }          
        }
        return ans;
    }
</pre>
