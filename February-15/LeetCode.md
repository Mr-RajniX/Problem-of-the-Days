## Problem of the Day - [<a href="https://leetcode.com/problems/add-to-array-form-of-integer/description"> 989. Add to Array-Form of Integer </a>]


#### ⭐<ins>Solution Function Code</ins> -
<pre>

    vector<int> addToArrayForm(vector<int>& num, int k) {
        
        int carry = 0;
        int j = num.size() - 1;

        while(j >= 0)
        {

         int sum = num[j] + (k % 10) + carry;
         k /= 10;

         num[j--] = sum % 10;
         carry = sum/10;

        }

        while(k > 0)
        {

         int sum = (k % 10) + carry;
         k /= 10;
    
         num.insert(num.begin(), sum%10);
         carry = sum/10;
       
        }

        if(carry > 0) num.insert(num.begin(), carry);
        
        return num;
    }

</pre>
