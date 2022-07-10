# [51. N-Queens (Hard)](https://leetcode.com/problems/n-queens/)

<p>The <strong>n-queens</strong> puzzle is the problem of placing <code>n</code> queens on an <code>n x n</code> chessboard such that no two queens attack each other.</p>

<p>Given an integer <code>n</code>, return <em>all distinct solutions to the <strong>n-queens puzzle</strong></em>.</p>

<p>Each solution contains a distinct board configuration of the n-queens' placement, where <code>'Q'</code> and <code>'.'</code> both indicate a queen and an empty space, respectively.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/11/13/queens.jpg" style="width: 600px; height: 268px;">
<pre><strong>Input:</strong> n = 4
<strong>Output:</strong> [[".Q..","...Q","Q...","..Q."],["..Q.","Q...","...Q",".Q.."]]
<strong>Explanation:</strong> There exist two distinct solutions to the 4-queens puzzle as shown above
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> n = 1
<strong>Output:</strong> [["Q"]]
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= n &lt;= 9</code></li>
</ul>


**Related Topics**:  
[Backtracking](https://leetcode.com/tag/backtracking/)

**Similar Questions**:
* [N-Queens II (Hard)](https://leetcode.com/problems/n-queens-ii/)
* [Grid Illumination (Hard)](https://leetcode.com/problems/grid-illumination/)

## Video Notes

![vlcsnap-2022-07-10-18h32m16s437](https://user-images.githubusercontent.com/37560890/178147782-41c707ac-10f6-48cd-8f77-e8cb16d51e70.png)
![vlcsnap-2022-07-10-18h36m09s467](https://user-images.githubusercontent.com/37560890/178147786-7d4ba334-0b83-4f93-a6be-a77d7722e166.png)
![vlcsnap-2022-07-10-18h36m38s692](https://user-images.githubusercontent.com/37560890/178147787-771dc0ef-d835-4c38-b6bb-1c1ff0c6f114.png)
![vlcsnap-2022-07-10-18h37m41s402](https://user-images.githubusercontent.com/37560890/178147789-e200d183-afd5-4c35-bac7-8ddc5282dd32.png)
![vlcsnap-2022-07-10-18h38m27s490](https://user-images.githubusercontent.com/37560890/178147790-29e77ac6-a5e1-4abe-8561-05a2fba7283a.png)
![vlcsnap-2022-07-10-18h46m44s821](https://user-images.githubusercontent.com/37560890/178147791-a6c5cad2-2db8-4301-b6a1-ffe3b9cc6ad2.png)
![vlcsnap-2022-07-10-18h49m04s636](https://user-images.githubusercontent.com/37560890/178147793-d9674107-6554-4919-87d0-bfc02e410957.png)
![vlcsnap-2022-07-10-18h49m16s713](https://user-images.githubusercontent.com/37560890/178147794-0411f68c-3b3a-4b1b-8ada-6dac233025dc.png)
![vlcsnap-2022-07-10-18h49m39s009](https://user-images.githubusercontent.com/37560890/178147795-da249e12-7d32-4e2c-86fa-470da6b9c894.png)
![vlcsnap-2022-07-10-18h52m19s295](https://user-images.githubusercontent.com/37560890/178147796-bd0c127f-86f6-495f-a9ca-48b3c77ac19d.png)
![vlcsnap-2022-07-10-18h52m43s739](https://user-images.githubusercontent.com/37560890/178147797-985564f6-9acc-4a39-a193-f0f9f2ac3725.png)
![vlcsnap-2022-07-10-18h56m08s785](https://user-images.githubusercontent.com/37560890/178147798-f76fdd77-f1c4-4689-b039-3196d9d7c276.png)
![vlcsnap-2022-07-10-18h59m21s467](https://user-images.githubusercontent.com/37560890/178147799-3856247c-b11d-45d1-b344-c1d81f507776.png)
![vlcsnap-2022-07-10-19h05m29s832](https://user-images.githubusercontent.com/37560890/178147800-bba4f890-970e-4d82-b19a-d62692674d47.png)
![vlcsnap-2022-07-10-19h05m57s385](https://user-images.githubusercontent.com/37560890/178147801-464c0699-6e22-483e-ad96-ddae3b7b1e03.png)
![vlcsnap-2022-07-10-19h06m05s389](https://user-images.githubusercontent.com/37560890/178147802-31776669-292f-417b-b2f5-41c440e92283.png)
![vlcsnap-2022-07-10-19h10m53s980](https://user-images.githubusercontent.com/37560890/178147804-d5dc17c2-7c4a-4697-b981-fa6ad784db11.png)
![vlcsnap-2022-07-10-19h11m25s556](https://user-images.githubusercontent.com/37560890/178147807-f2fa7df2-d931-4fb4-8a40-6d7aef89f076.png)
![image](https://user-images.githubusercontent.com/37560890/178147982-6a8c4de0-c97c-428a-8a57-b6a61d38ed21.png)


## Solution 1. Backtracking

```cpp
// OJ: https://leetcode.com/problems/n-queens/
// Time: O(N!)
// Space: O(N^2)

class Solution 
{
public:
    
    bool issafe(int row,int col, vector<string> board,int n)
    {
        // Check for the upper diagonal
        while(row>=0 and col>=0 )
        {
            if(board[row][col] == 'Q') return false;
            row--;
            col--;
        }
        
        // Check for left row
        while(col>=0)
        {
            if(board[row][col]== 'Q') return false;
            col--;
        }
        
        // Downward diagonal
        while(row<n and col>=0)
        {
            if(board[row][col]=='Q') return false;
            row++;
            col--;
        }
        return true;
    }
    
    void solve(int col,vector<string> &board,vector<vector<string>> &ans,int n)
    {
        // If the col == n then it's out of bound then we got our ans
        if(col==n)
        {
            ans.push_back(board);
            return;
        }
        
        // Travel for every row
        for(int row= 0;row<n;row++)
        {
            // Is safe function calling if true then place the queen
            if(issafe(row,col,board,n))
            {
                board[row][col] = 'Q';
                
                // Solve and place the queen for the next row
                solve(col+1,board,ans,n);
                
                // Backtracking step - Coming back omit this Q 
                // And place it to the next row
                board[row][col]='.';
                
            }
        }
    }
    
    vector<vector<string>> solveNQueens(int n) 
    {
        // Create the ans vector
        vector<vector<string>> ans;
        
        // Create the board array
        vector<string> board(n);
        
        // Create the empty string
        string s(n,'.');
        
        // Fill board with empty string
        for(int i=0;i<n;i++)
        {
            board[i] =s;
        }
        
        // Calling the recursive function
        solve(0,board,ans,n);
        
        // Finally return the ans
        return ans;
        
    }
};

```

## Solution 2. Backtracking

```cpp
// OJ: https://leetcode.com/problems/n-queens/
// Time: O(N!)
// Space: O(N^2)

class Solution 
{
public:
    vector<vector<string>> ret;
    bool is_valid(vector<string> &board, int row, int col)
    {
        // check col
        for(int i=row;i>=0;--i) if(board[i][col] == 'Q') return false;
        
	// check left diagonal
        for(int i=row,j=col;i>=0&&j>=0;--i,--j) if(board[i][j] == 'Q') return false;
        
	//check right diagonal
        for(int i=row,j=col;i>=0&&j<board.size();--i,++j) if(board[i][j] == 'Q') return false;
        
	// Finally return true
	return true;
    }
    
    void dfs(vector<string> &board, int row)
    {
        // exit condition
        if(row == board.size())
	{
            ret.push_back(board);
            return;
        }
        // iterate every possible position
        
	for(int i=0;i<board.size();++i)
	{
            if(is_valid(board,row,i))
	    {
                // make decision
                board[row][i] = 'Q';
                // next iteration
                dfs(board,row+1);
                // back-tracking
                board[row][i] = '.';
            }
        }
    }
    vector<vector<string>> solveNQueens(int n) 
    {
	// return empty if n <= 0
        if(n <= 0) return {{}};
        
	// Create the board vector for o/p ans
	vector<string> board(n,string(n,'.'));
	
	// Calling the recursive function
        dfs(board,0);
	
	// Finally return the result
        return ret;
    }
};

```


