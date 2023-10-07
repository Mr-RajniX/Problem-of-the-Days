### Problem of the Day : [Find All Four Sum Numbers]()

##### Solution :
<pre>
  vector< vector< int> > fourSum(vector< int> &arr, int k) {
        // Your code goes here
        vector< vector< int>>ans;
        sort(arr.begin(),arr.end());
        for(int i=0;i < arr.size();i++){
            for(int j=i+1;j < arr.size();j++){
                int lo = j+1, hi = arr.size()-1;
                while(lo < hi){
                    int sum = arr[i]+arr[lo]+arr[j]+arr[hi];
                    
                    if(sum < k){
                        lo++;
                    }
                    else if(sum > k){
                        hi--;
                    }
                    else{
                        ans.push_back({arr[i],arr[j],arr[lo],arr[hi]});
                        lo++;hi--;
                    }
                }
            }
        }
        set< vector< int>>s;
        for(auto &vec:ans){
            s.insert(vec);
        }
        vector< vector< int>>ans1;
        for(auto vec:s){
            ans1.push_back(vec);
        }
        return ans1;
    
    }
</pre>
