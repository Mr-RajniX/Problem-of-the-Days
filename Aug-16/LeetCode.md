### Problem of the Day {`Kyō no mondai`} : [239. Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/)

#### Solution {`Kaiketsu`}:
<pre>
  vector < int > maxSlidingWindow(vector < int > & nums, int k) {
        int n = nums.size();
        deque < int > flash;
        vector < int > ans(n-k+1);

        for(int i = 0; i < n; i++){
            while(!flash.empty() && nums[i] >= nums[flash.back()]) 
                flash.pop_back();
            flash.push_back(i);  
            if (flash.front() == i-k) 
                flash.pop_front(); 
            if (i >= k-1)
                ans[i-k+1]=nums[flash.front()]; 
        }
        return ans;
    }
</pre>
