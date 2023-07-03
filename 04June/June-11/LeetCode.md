## Problem of the Day - [<a href="https://leetcode.com/problems/snapshot-array/"> 1146. Snapshot Array </a>]


#### ⭐<ins>Solution Function Code #1</ins> -
<pre>

  vector<map<int,int>>v;
  int s=0;
    SnapshotArray(int length){
        v.resize(length);
        for(int i=0;i < length;i++){
            v[i][0]=0;
        }
    }
    void set(int index, int val){
        v[index][s]=val;
    }   
    int snap(){
        s++;
       return s-1;
    }   
    int get(int index, int snap_id){
        if(v[index].find(snap_id)==v[index].end()){
            auto it= --v[index].lower_bound(snap_id);
            return it->second;
        }
        return v[index][snap_id];
    }
</pre>
