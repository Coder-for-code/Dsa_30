# [37. Sudoku Solver (Hard)](https://leetcode.com/problems/sudoku-solver/)

<p>Write a program to solve a Sudoku puzzle by filling the empty cells.</p>

<p>A sudoku solution must satisfy <strong>all of the following rules</strong>:</p>

<ol>
	<li>Each of the digits <code>1-9</code> must occur exactly once in each row.</li>
	<li>Each of the digits <code>1-9</code> must occur exactly once in each column.</li>
	<li>Each of the digits <code>1-9</code> must occur exactly once in each of the 9 <code>3x3</code> sub-boxes of the grid.</li>
</ol>

<p>The <code>'.'</code> character indicates empty cells.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/ff/Sudoku-by-L2G-20050714.svg/250px-Sudoku-by-L2G-20050714.svg.png" style="height:250px; width:250px">
<pre><strong>Input:</strong> board = [["5","3",".",".","7",".",".",".","."],["6",".",".","1","9","5",".",".","."],[".","9","8",".",".",".",".","6","."],["8",".",".",".","6",".",".",".","3"],["4",".",".","8",".","3",".",".","1"],["7",".",".",".","2",".",".",".","6"],[".","6",".",".",".",".","2","8","."],[".",".",".","4","1","9",".",".","5"],[".",".",".",".","8",".",".","7","9"]]
<strong>Output:</strong> [["5","3","4","6","7","8","9","1","2"],["6","7","2","1","9","5","3","4","8"],["1","9","8","3","4","2","5","6","7"],["8","5","9","7","6","1","4","2","3"],["4","2","6","8","5","3","7","9","1"],["7","1","3","9","2","4","8","5","6"],["9","6","1","5","3","7","2","8","4"],["2","8","7","4","1","9","6","3","5"],["3","4","5","2","8","6","1","7","9"]]
<strong>Explanation:</strong>&nbsp;The input board is shown above and the only valid solution is shown below:

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/Sudoku-by-L2G-20050714_solution.svg/250px-Sudoku-by-L2G-20050714_solution.svg.png" style="height:250px; width:250px">
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>board.length == 9</code></li>
	<li><code>board[i].length == 9</code></li>
	<li><code>board[i][j]</code> is a digit or <code>'.'</code>.</li>
	<li>It is <strong>guaranteed</strong> that the input board has only one solution.</li>
</ul>


**Companies**:  
[DoorDash](https://leetcode.com/company/doordash), [Microsoft](https://leetcode.com/company/microsoft), [Amazon](https://leetcode.com/company/amazon), [Google](https://leetcode.com/company/google), [Intuit](https://leetcode.com/company/intuit), [Bloomberg](https://leetcode.com/company/bloomberg), [Adobe](https://leetcode.com/company/adobe), [Uber](https://leetcode.com/company/uber)

**Related Topics**:  
[Array](https://leetcode.com/tag/array/), [Backtracking](https://leetcode.com/tag/backtracking/), [Matrix](https://leetcode.com/tag/matrix/)

**Similar Questions**:
* [Valid Sudoku (Medium)](https://leetcode.com/problems/valid-sudoku/)
* [Unique Paths III (Hard)](https://leetcode.com/problems/unique-paths-iii/)

## Video Notes
![vlcsnap-2022-07-10-21h43m55s781](https://user-images.githubusercontent.com/37560890/178153791-f984743a-4172-41b1-9cee-fe46e93d0961.png)
![vlcsnap-2022-07-10-21h45m16s457](https://user-images.githubusercontent.com/37560890/178153793-eaafe893-013f-431c-8d34-1a3055b531b2.png)
![vlcsnap-2022-07-10-21h45m35s259](https://user-images.githubusercontent.com/37560890/178153794-be4d5913-3f2d-448e-b221-6bfe825210bb.png)
![vlcsnap-2022-07-10-21h47m05s591](https://user-images.githubusercontent.com/37560890/178153796-62ebe742-36a3-4d6d-b537-084c6200eb92.png)
![vlcsnap-2022-07-10-21h49m37s486](https://user-images.githubusercontent.com/37560890/178153799-82187b50-9649-460c-9b0f-17f018a136e3.png)
![vlcsnap-2022-07-10-21h49m58s956](https://user-images.githubusercontent.com/37560890/178153800-cb82cc6b-73da-4708-8a4b-e72a983b940f.png)
![vlcsnap-2022-07-10-21h50m35s292](https://user-images.githubusercontent.com/37560890/178153801-7c1efa76-d8ae-439d-979b-3acd21eb1668.png)
![vlcsnap-2022-07-10-21h50m51s663](https://user-images.githubusercontent.com/37560890/178153803-d9858c83-0022-4cb4-9e92-7a2c34d0c676.png)
![vlcsnap-2022-07-10-21h51m00s676](https://user-images.githubusercontent.com/37560890/178153804-e0032968-99eb-428c-829a-e69fd915a601.png)
![vlcsnap-2022-07-10-21h51m15s743](https://user-images.githubusercontent.com/37560890/178153805-0cc5a072-adeb-425e-99d9-6b871cc8326a.png)
![vlcsnap-2022-07-10-21h51m52s768](https://user-images.githubusercontent.com/37560890/178153807-fb666364-ec30-4822-a876-8c90793c1a30.png)
![vlcsnap-2022-07-10-21h52m19s188](https://user-images.githubusercontent.com/37560890/178153809-5bfb256c-56c0-44d4-9838-d340ef78e6b4.png)
![vlcsnap-2022-07-10-21h58m16s161](https://user-images.githubusercontent.com/37560890/178153812-0cb041a6-14e2-472b-b34c-137daaa65b8c.png)
![vlcsnap-2022-07-10-22h04m55s833](https://user-images.githubusercontent.com/37560890/178153813-4b00bb6c-d870-4f2b-8123-2023d75fe223.png)
![vlcsnap-2022-07-10-22h05m26s965](https://user-images.githubusercontent.com/37560890/178153816-6c5e1ef7-bbdf-4fb4-a0c5-91ec84350d2b.png)



## Solution 1. Backtracking

```cpp
// OJ: https://leetcode.com/problems/sudoku-solver/
// Time: O((9!)^9)
// Space: O(81)

class Solution
{
public:
    
    bool solve(vector<vector<char>>& board)
    {
        // Travel in the matrix and find the empty box
        for(int i=0;i<board.size();i++)
        {
            for(int j=0;i<board[0].size();j++)
            {
                // If board empty then enter 
                if(board[i][j]=='.')
                {
                    // Check for all the possibilty from 1 to 9
                    for(char c='1'; c<='9';c++)
                    {
                        // Isvalid checking function if yes then enter
                        if(isValid(board,i,j,c))
                        {
                            // If yes then assign c to that box
                            board[i][j]=c;
                            
                            // Calling the other calls
                            if(solve(board)==true)  return true;
                            
                            else board[i][j]= '.';
                        }
                    }
                    return false;
                }
            }
        }
        return true; 
    }
    
    bool isValid(vector<vector<char>> &board,int row,int col,char c)
    {
        for(int i=0;i<9;i++)
        {
            // Checking for the column
            if(board[i][col]==c) return false;
            
            // Checking for the row
            if(board[row][i]==c) return false;
            
            // Checking for the 3*3 subboxes 
            if(board[3*(row/3)+i/3][3*(col/3)+i%3]==c) return false;
                
        }
        
        return true;
    }
    
    void solveSudoku(vector<vector<char>>& board) 
    {
        // Calling the recursive method
        solve(board);
    }
};
```

or

```cpp
//Solution 01:

class Solution
{
public:
    void solveSudoku(vector<vector<char>>& board) 
    {
        solve(board);
    }
    
    bool solve(vector<vector<char>>& board)
    {
        for(int i=0; i<board.size(); i++)
	{
            for(int j=0; j<board[0].size(); j++)
	    {
                if(board[i][j] == '.')
		{
                    for(char c='1'; c<='9'; c++)
		    {
                        if(valid(c, board, i, j))
			{
                            board[i][j] = c;
                            if(solve(board) == true) return true;
                            else board[i][j]='.';
                        }
                    }
                    return false;
                }
            }
        }
        return true;
    }
    
    bool valid(char c, vector<vector<char>>& board, int row, int col)
    {
        for(int i=0; i<9; i++)
	{
            if(board[i][col] == c) return false;
            if(board[row][i] == c) return false;
            if(board[3*(row/3)+(i/3)][3*(col/3)+(i%3)] == c) return false;
        }
        return true;
    }
};
```
