### Problem of the Day : [1125. Smallest Sufficient Team](https://leetcode.com/problems/smallest-sufficient-team/)

#### Solution :
<pre>
  vector< int > smallestSufficientTeam(vector< string >& req_skills, vector< vector< string >>& people) {
        int n = req_skills.size(); int m =  people.size();
        unordered_map< string, int > skillIndex;
        for(int i=0 ; i < n; i++) skillIndex[req_skills[i]] = i;

        vector< int > arr(m,0);
        for(int i=0 ; i < m; i++){
            vector< string> &personSkill =  people[i];
            int val = 0;
            for( const string& skill : personSkill) val |= 1 << skillIndex[skill];
            arr[i] = val;
        }
        vector < bool > banned(m, false);
        for (int i = 0; i < m; i++) {
            for (int j = i + 1; j < m; j++) {
                int val = arr[i] | arr[j];
                if (val == arr[i]) {
                    banned[j] = true;
                }
                else if (val == arr[j]) {
                    banned[i] = true;
                }
            }
        }
        vector < int > ans;
        helper(0, n, arr, vector< int >(), banned, ans);
        
        return ans;
    }
    void helper(int cur, int n, const vector< int >& arr, vector< int > team, const vector< bool >& banned, vector< int >& ans) {
        if (cur == (1 << n) - 1) {
            if (ans.empty() || team.size() < ans.size()) {
                ans = team;
            }
            return;
        }
        
        if (!ans.empty() && team.size() >= ans.size()) {
            return;
        }
        
        int zero = 0;
        while (((cur >> zero) & 1) == 1) {
            zero++;
        }
        
        for (int i = 0; i < arr.size(); i++) {
            if (banned[i]) {
                continue;
            }
            
            if (((arr[i] >> zero) & 1) == 1) {
                team.push_back(i);
                helper(cur | arr[i], n, arr, team, banned, ans);
                team.pop_back();
            }
        }
    }
</pre>
