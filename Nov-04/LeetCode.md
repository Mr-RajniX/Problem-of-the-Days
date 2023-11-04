#### Problem of the Day : [1503. Last Moment Before All Ants Fall Out of a Plank](https://leetcode.com/problems/last-moment-before-all-ants-fall-out-of-a-plank/)

#### Solution :
<pre>
  int getLastMoment(int n, vector< int>& left, vector< int>& right) {
        int ans=0;
        for(int i=0;i < left.size();i++) 
            ans=max(ans,(abs(0-left[i])));  
        for(int i=0;i < right.size();i++)
            ans=max(ans,abs(n-right[i]));        
        return ans; 
    }
</pre>
