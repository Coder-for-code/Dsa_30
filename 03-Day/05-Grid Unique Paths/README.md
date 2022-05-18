5. https://leetcode.com/problems/unique-paths/

![10](https://user-images.githubusercontent.com/37560890/168953000-059339a9-a6ff-4b88-95d3-d76bedf97ef7.jpg)
![9](https://user-images.githubusercontent.com/37560890/168953006-8cf41b98-f4a8-4beb-b5f4-6448601e7454.jpg)

```cpp
Solution 1: 

Approach: 
The problem states that we can either move rightward or downward direction. 
So we recursively try out all the possible combinations.

#include<bits/stdc++.h>
using namespace std;

class Solution
{
public:
    int countPaths(int i,int j,int n,int m)
    {
        if(i==(n-1)&&j==(m-1)) return 1;
        if(i>=n||j>=m) return 0;
        else return countPaths(i+1,j,n,m)+countPaths(i,j+1,n,m);
    }
    
    int uniquePaths(int m, int n) 
    {
       return countPaths(0,0,m,n);
    }
};

int main()
{
    Solution obj;
    int totalCount= obj.uniquePaths(3,7);
    cout<<"The total number of Unique Paths are "<<totalCount<<endl;
}

Time Complexity: The time comp[lexity of this recursive solution is exponential.
Space Complexity: As we are using stack space for recursion so the space complexity will also be exponential.

```
![image](https://user-images.githubusercontent.com/37560890/168953191-aa71f631-9613-400a-863f-5406e8902879.png)

```cpp
Solution 2: Dynamic Programming Solution

Intuition: 

The dynamic programming solution of this problem is a bit extension of the recursive solution.
In recursive solutions, there are many overlapping subproblems. 
In this solution instead of traversing all the possible paths, whenever we get the result we’ll store it in a matrix for future use. 
Whenever we encounter the same subproblem we directly get the value from the matrix instead of recomputing it. 
By this memorization technique, we can avoid the recomputation and the time complexity will be drastically reduced. 
This is the main intuition behind this dynamic programming solution.

#include<bits/stdc++.h>
using namespace std;

class Solution
{
public:
    int countPaths(int i,int j,int n,int m,vector<vector<int>> &dp)
    {
        if(i==(n-1)&&j==(m-1)) return 1;
        if(i>=n||j>=m) return 0;
        if(dp[i][j]!=-1) return dp[i][j];
        else return dp[i][j]=countPaths(i+1,j,n,m,dp)+countPaths(i,j+1,n,m,dp);
        
    }
    
    int uniquePaths(int m, int n) 
    {
        vector<vector<int>> dp(m+1,vector<int>(n+1,-1));
       
        //dp[1][1]=1;
       int num=countPaths(0,0,m,n,dp);
        if(m==1&&n==1)
            return num;
        return dp[0][0];
    }
};
int main()
{
    Solution obj;
    int totalCount= obj.uniquePaths(3,7);
    cout<<"The total number of Unique Paths are "<<totalCount<<endl;
}

Time Complexity: The time complexity of this solution will be O(n*m) because at max there can be n*m number of states.
Space Complexity: As we are using extra space for the dummy matrix the space complexity will also be O(n*m).
```
![image](https://user-images.githubusercontent.com/37560890/168953453-25b28e85-3c04-4af9-9bfb-c544e823c88d.png)

```cpp

Solution 3: Combinatorics Solution
#include<bits/stdc++.h>
using namespace std;

class Solution 
{
public:
    int uniquePaths(int m, int n) 
    {
            int N = n + m - 2;
            int r = m - 1; 
            double res = 1;
            
            for (int i = 1; i <= r; i++)
                res = res * (N - r + i) / i;
            return (int)res;
    }
};

int main()
{
    Solution obj;
    int totalCount= obj.uniquePaths(2,3);
    cout<<"The total number of Unique Paths are "<<totalCount<<endl;
}

Time Complexity: The time complexity of this solution will be O(n-1) or  O(m-1) depending on the formula we are using.
Space Complexity: As we are not using any extra space the space complexity of the solution will be  O(1).

```
![image](https://user-images.githubusercontent.com/37560890/168953684-3f0f0d65-6e1f-41dd-9daf-35ea1afcc1c4.png)
