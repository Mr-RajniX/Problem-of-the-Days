#### Problem of the Day : [2391. Minimum Amount of Time to Collect Garbage](https://leetcode.com/problems/minimum-amount-of-time-to-collect-garbage/)

#### Solution :
<pre>
  int garbageCollection(vector< string>& garbage, vector< int>& travel) {
        ios_base::sync_with_stdio(0),cout.tie(0),cin.tie(0);
        int trucks[3]={},last[3]={};
        int ans=0,n=garbage.size();
        vector< int>pref(n);
        for(int i=0;i < n;i++){
            bool G=0,P=0,M=0;
            for(auto &it:garbage[i]){
                trucks[trans(it)]++;
                if(it=='G')G=1;
                if(it=='P')P=1;
                if(it=='M')M=1;
            }
            if(i){
                for(int j=0;j < 3;j++)
                    last[j]+=travel[i-1];
                if(G)trucks[0]+=last[0],last[0]=0;
                if(P)trucks[1]+=last[1],last[1]=0;
                if(M)trucks[2]+=last[2],last[2]=0;
            }
        }
        return trucks[0]+trucks[1]+trucks[2];
    }
    int trans(char a){
        if(a=='G')
            return 0;
        if(a=='P')
            return 1;
        return 2;
    }
</pre>
