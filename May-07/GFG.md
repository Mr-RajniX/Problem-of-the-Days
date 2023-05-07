## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/d385b9d635b7b10eef6bf365b84922aaeec9eb98/1"> String Mirror </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

   string stringMirror(string str){
        int n = str.size();
        string left = "", right = "";
        left += str[0];
        right += str[0];
        string ans(n, 'z');
        for(int i = 1; i < n; i++)
        {
            if(str[i] > str[i - 1])
            {
                break;
            }
            string temp = left + right;
            if(temp < ans)ans = temp;
            left += str[i];
            right = str[i] + right;
            
            
        }
        string temp = left + right;
        if(temp < ans)ans = temp;
        
        return ans;
    }
</pre>
