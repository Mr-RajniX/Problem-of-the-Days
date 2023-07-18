### Problem of the Day : [Longest Repeating Subsequence](https://practice.geeksforgeeks.org/problems/longest-repeating-subsequence2004/1)

#### Solution :
<pre>
  int LongestRepeatingSubsequence(string str){
		        int l=str.length();
            vector< int > prev(l+1, 0);
            vector< int > curr(l+1);
            curr[0]=0;
            for(int i=0; i < l; i++) {
                for(int j=0; j < l; j++) {
                    if(i!=j && str[i]==str[j]) {
                        curr[j+1]=1+prev[j];
                    }
                    else {
                        curr[j+1]=max(curr[j], prev[j+1]);
                    }
                }
                prev=curr;
            }
            return prev[l];
		}
</pre>
