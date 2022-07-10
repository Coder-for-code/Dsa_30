# [47. Permutations II (Medium)](https://leetcode.com/problems/permutations-ii/)

<p>Given a collection of numbers, <code>nums</code>,&nbsp;that might contain duplicates, return <em>all possible unique permutations <strong>in any order</strong>.</em></p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> nums = [1,1,2]
<strong>Output:</strong>
[[1,1,2],
 [1,2,1],
 [2,1,1]]
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> nums = [1,2,3]
<strong>Output:</strong> [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 8</code></li>
	<li><code>-10 &lt;= nums[i] &lt;= 10</code></li>
</ul>


**Related Topics**:  
[Backtracking](https://leetcode.com/tag/backtracking/)

**Similar Questions**:
* [Next Permutation (Medium)](https://leetcode.com/problems/next-permutation/)
* [Permutations (Medium)](https://leetcode.com/problems/permutations/)
* [Palindrome Permutation II (Medium)](https://leetcode.com/problems/palindrome-permutation-ii/)
* [Number of Squareful Arrays (Hard)](https://leetcode.com/problems/number-of-squareful-arrays/)

## Video Notes
![image](https://user-images.githubusercontent.com/37560890/178135857-6621523b-ec8f-4629-adc0-55b86a52b8f0.png)


## Solution 1.

Similar idea as the DFS solution to [46. Permutations (Medium)](../46.%20Permutations).

But since there are duplicates, we shouldn't swap the `nums[start]` with the same digit twice.

To prevent this from happening, we need to do several modifications:
1. Sort the array at the beginning
1. If `nums[i] == nums[start] (i != start)` then should skip the swap, because this swap won't make any change to the array. In other words, the `nums[start]` represents the digit we tried last time, so we shouldn't try its duplicate again.
1. We can't pass `nums` by reference. We have to copy the array in each DFS step. Because the previous point is based on the assumption that the numbers after `nums[i]` are sorted so that the duplicates following `nums[i]` are skipped. If we pass by reference, the numbers after `nums[i]` might be unsorted, which breaks the assumption.

The drawback of this solution is that we need to keep copying the `nums` array during DFS, which adds time and space complexity.

```cpp
// OJ: https://leetcode.com/problems/permutations-ii
// Time: O(N! * N)
// Space: O(N^2)
// Ref: https://discuss.leetcode.com/topic/8831/a-simple-c-solution-in-only-20-lines

class Solution 
{
public:
    void recursion(vector<int> num, int i, int j, vector<vector<int> > &res) 
    {
        if (i == j-1) {
            res.push_back(num);
            return;
        }
        
	for (int k = i; k < j; k++) 
	{
            if (i != k && num[i] == num[k]) continue;
            swap(num[i], num[k]);
            recursion(num, i+1, j, res);
        }
    }
    vector<vector<int> > permuteUnique(vector<int> &num) 
    {
        sort(num.begin(), num.end());
        vector<vector<int> >res;
        recursion(num, 0, num.size(), res);
        return res;
    }
};
```
