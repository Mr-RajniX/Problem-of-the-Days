### Problem of the Day : [Palindrome String](https://practice.geeksforgeeks.org/problems/palindrome-string0817/1)

#### Solution :
<pre>
  int isPalindrome(string S){
	    int s = 0, e = S.size()-1;
	    while(s < e){
	        if(S[s++] != S[e--])    
                  return 0;
	    }
	    return 1;
	}
</pre>
