#### Problem of the Day : [Print Matrix in snake Pattern](https://www.geeksforgeeks.org/problems/print-matrix-in-snake-pattern-1587115621/1)

#### Solution :
<pre>
  vector< int> snakePattern(vector< vector< int> > matrix){   
        vector< int> snake;
        for(int idx = 0; idx < matrix.size();idx++){
            if(idx % 2 == 0)
             snake.insert(snake.end(),matrix[idx].begin(),matrix[idx].end());
            else
             snake.insert(snake.end(),matrix[idx].rbegin(),matrix[idx].rend());
        }
        return snake;
    }
</pre>
