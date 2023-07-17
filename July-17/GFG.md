### Problem of the Day : [First non-repeating character in a stream](https://practice.geeksforgeeks.org/problems/first-non-repeating-character-in-a-stream1216/1)

#### Solution :
<pre>
  string FirstNonRepeating(string A){
		    map < char, int > count;
		    string ans;
		    vector < char > v;
		    
		    for(char ch : A){
		        if(count.find(ch) == count.end()){
		            v.push_back(ch); count[ch] =1;
		        }
		        else{
		            int index = find(v.begin(), v.end() , ch) - v.begin();
		            if (index < v.size())
		                v.erase(v.begin() + index);
		        }ans += (v.empty() ? '#' : v.front());
		    }
		    return ans;
		}
</pre>
