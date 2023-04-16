## Problem of the Day - [<a href="https://practice.geeksforgeeks.org/problems/4db2fcd97400456c4914d5a3e8ad932cc21e3e9d/1"> Unequal Arrays </a>]


#### ⭐<ins>Solution Function Code </ins> -


    long long solve(int n, vector<int> &a, vector<int> &b) {
        // code here
        vector<int>oa;
        vector<int>ea;
        vector<int>ob;
        vector<int>eb;
        for(int i=0;i<n;i++)
        {
            if(a[i]%2==0) ea.push_back(a[i]);
            else oa.push_back(a[i]);
            
            if(b[i]%2==0) eb.push_back(b[i]);
            else ob.push_back(b[i]);
        }
        
        if(oa.size()!=ob.size() || ea.size()!=eb.size()) return -1;
        
        sort(oa.begin(),oa.end());
        sort(ob.begin(),ob.end());sort(ea.begin(),ea.end());sort(eb.begin(),eb.end());
        
        long long count1=0,count2=0,c1=0,c2=0;
        for(int i=0;i<oa.size();i++)
        {
            
            count1+=(oa[i]-ob[i]);
            c1+=abs(oa[i]-ob[i])/2;
        }
        
        for(int i=0;i<ea.size();i++)
        {
            count2+=(ea[i]-eb[i]);
            c2+=abs(ea[i]-eb[i])/2;
        }
        
        return count1+count2==0?(c1+c2)/2:-1;
    }

