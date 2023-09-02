### Problem of the Day : [Find the string in grid](https://practice.geeksforgeeks.org/problems/find-the-string-in-grid0111/1)

#### Solution :
<pre>
  private:
    bool right(int r, int c, vector< vector< char > >&grid, string &word){
        int ind = 0;
        int n=grid.size(), m=grid[0].size();
        for(int i=c; i < m; i++){
            if(ind < word.length()){
                if(word[ind]!=grid[r][i]) return false;
                ind++;
            }
            else return true;
        }
        return ind==word.length();
    }
    bool left(int r, int c, vector< vector< char > >&grid, string &word){
        int ind = 0;
        int n=grid.size(), m=grid[0].size();
        for(int i=c; i >= 0; i--){
            if(ind < word.length()){
                if(word[ind]!=grid[r][i]) return false;
                ind++;
            }
            else return true;
        }
        return ind==word.length();
    }
    bool up(int r, int c, vector< vector< char > >&grid, string &word){
        int ind = 0;
        int n=grid.size(), m=grid[0].size();
        for(int i=r; i >= 0; i--){
            if(ind<word.length()){
                if(word[ind]!=grid[i][c]) return false;
                ind++;
            }
            else return true;
        }
        return ind==word.length();
    }
    bool down(int r, int c, vector< vector< char > >&grid, string &word){
        int ind = 0;
        int n=grid.size(), m=grid[0].size();
        for(int i=r; i < n; i++){
            if(ind < word.length()){
                if(word[ind]!=grid[i][c]) return false;
                ind++;
            }
            else return true;
        }
        return ind==word.length();
    }
    bool lud(int r, int c, vector< vector< char > >&grid, string &word){
        int ind = 0;
        int n=grid.size(), m=grid[0].size();
        for(int i=0; r-i >= 0 && c-i >= 0; i++){
            if(ind < word.length()){
                if(word[ind]!=grid[r-i][c-i]) return false;
                ind++;
            }
            else return true;
        }
        return ind==word.length();
    }
    bool lld(int r, int c, vector< vector< char > >&grid, string &word){
        int ind = 0;
        int n=grid.size(), m=grid[0].size();
        for(int i=0; r+i < n && c-i >= 0; i++){
            if(ind < word.length()){
                if(word[ind]!=grid[r+i][c-i]) return false;
                ind++;
            }
            else return true;
        }
        return ind==word.length();
    }
    bool rud(int r, int c, vector< vector< char > >&grid, string &word){
        int ind = 0;
        int n=grid.size(), m=grid[0].size();
        for(int i=0; r-i >= 0 && c+i < m; i++){
            if(ind < word.length()){
                if(word[ind]!=grid[r-i][c+i]) return false;
                ind++;
            }
            else return true;
        }
        return ind==word.length();
    }
    bool rld(int r, int c, vector< vector< char > >&grid, string &word){
        int ind = 0;
        int n=grid.size(), m=grid[0].size();
        for(int i=0; r+i < n && c+i < m; i++){
            if(ind < word.length()){
                if(word[ind]!=grid[r+i][c+i]) return false;
                ind++;
            }
            else return true;
        }
        return ind==word.length();
    }
    bool f(int i, int j, vector< vector< char > >&grid, string &word){
        bool flag = right(i, j,  grid, word) | 
                    left(i, j, grid, word) |
                    up(i, j, grid, word) |
                    down(i, j, grid, word) |
                    lud(i, j, grid, word) |
                    lld(i, j, grid, word) |
                    rud(i, j, grid, word) |
                    rld(i, j, grid, word);
        return flag;
    }
public:
	vector < vector < int > >searchWord(vector< vector< char > >grid, string word){
	    // Code here
	    vector<vector<int>> ans;
        int n=grid.size(), m=grid[0].size();
	    for(int i=0; i < n; i++){
	        for(int j=0; j < m; j++){
	            bool flag = f(i, j, grid, word);
	            if(flag) ans.push_back({i, j});
	        }
	    }
	    return ans;
	}
</pre>
