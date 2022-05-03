4. https://leetcode.com/problems/pascals-triangle/

![6](https://user-images.githubusercontent.com/37560890/166399516-c180e9d3-1c68-4ada-af19-fe48dfee0a1c.jpg)

```cpp
class Solution 
{
public:
    vector<vector<int> > generate(int numRows) 
    {
        vector<vector<int>> r(numRows);

        for (int i = 0; i < numRows; i++) 
        {
            r[i].resize(i + 1);
            r[i][0] = r[i][i] = 1;
  
            for (int j = 1; j < i; j++)
                r[i][j] = r[i - 1][j - 1] + r[i - 1][j];
        }
        
        return r;
    }
};
```
