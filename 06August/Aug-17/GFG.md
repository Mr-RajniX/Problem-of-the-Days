### Problem of the day : [Next Smallest Palindrome](https://practice.geeksforgeeks.org/problems/next-smallest-palindrome4740/1)

#### Solution :
<pre>
  vector< int > generateNextPalindrome(int num[], int n) {
        vector< int > ans;
        if(n == 1){
            if(num[0] == 9){
                ans.push_back(1);
                ans.push_back(1);
                return ans;
            }
            else{
                ans.push_back(num[0] + 1);
                return ans;
            }
        }
        int l = 0;
        int r = n -1;
        bool flag = true;
        bool changed = false;
        while(l < r){
            if(num[r] > num[l]){
                num[r] = num[l];
                flag = false;
            }
            else if(num[r] < num[l]){
                num[r] = num[l];
                flag = true;
                changed = true;
            }
            l++;
            r--;
        }
        
        if(flag == false || changed == false){
            if(n%2 == 0) {
                l--;
                r++;
            }
            while(num[l] == 9 && num[r] == 9 && l >=0 && r <n){
                num[l] = 0;
                num[r] = 0;
                l--;
                r++;
            }
            if(l <0){
                num[0] = 1;
                for(int i = 0; i< n;i++)
                    ans.push_back(num[i]);
                ans.push_back(1);
                return ans;
            }
            
            if(l == r && l >=0 && r <=n)
                num[l] +=1;
            else if (l>=0 && r <=n) {
                num[l] +=1;
                num[r] +=1;
            }
            
        }
        for(int i = 0; i< n;i++)
            ans.push_back(num[i]);
        return ans;
    }
</pre>
