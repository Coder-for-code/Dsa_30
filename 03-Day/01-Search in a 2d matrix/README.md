4. https://leetcode.com/problems/search-a-2d-matrix/ 

![1](https://user-images.githubusercontent.com/37560890/168951257-12dc6648-243c-4422-9631-3d23dc1acd68.jpg)
![2](https://user-images.githubusercontent.com/37560890/168951262-77a2a8a7-e16b-4a74-8662-3089cb20a5ed.jpg)
![3](https://user-images.githubusercontent.com/37560890/168951267-ad2e4e27-4c51-402c-8423-f901e1d5e709.jpg)

```cpp
Solution 1: Naive approach

Approach: 
1. We can traverse through every element that is present in the matrix and 
return true if we found any element in the matrix is equal to the target integer.

2. If the traversal is finished we can directly return false as 
we did not find any element in the matrix to be equal to the target integer.

Time complexity: O(m*n)
Space complexity: O(1)
```

```cpp
Solution 2: [Efficient] – Binary search

Intuition: 

1. As it is clearly mentioned that the given matrix will be row-wise and column-wise sorted,
we can see that the elements in the matrix will be in a monotonically increasing order.

2. So we can apply binary search to search the matrix. Consider the 2D matrix as a 1D matrix 
having indices from 0 to (m*n)-1 and apply binary search. 

3. Below the available image is the visual representation of the indices of 3*4 matrix.

class Solution
{
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) 
    {
        int lo = 0;
        if(!matrix.size()) return false;
        int hi = (matrix.size() * matrix[0].size()) - 1;
        
        while(lo <= hi) 
	{
            int mid = (lo + (hi - lo) / 2);
            if(matrix[mid/matrix[0].size()][mid % matrix[0].size()] == target) 
	    {
                return true;
            }
            
	    if(matrix[mid/matrix[0].size()][mid % matrix[0].size()] < target) 
	    {
                lo = mid + 1;
            }
            
	    else 
	    {
                hi = mid - 1;
            }
        }
        return false;
    }
};

Time complexity: O(log(m*n))
Space complexity: O(1)
```
