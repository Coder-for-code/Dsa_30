# [90. Subsets II (Medium)](https://leetcode.com/problems/subsets-ii/)

<p>Given an integer array <code>nums</code> that may contain duplicates, return <em>all possible subsets (the power set)</em>.</p>

<p>The solution set <strong>must not</strong> contain duplicate subsets. Return the solution in <strong>any order</strong>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<pre><strong>Input:</strong> nums = [1,2,2]
<strong>Output:</strong> [[],[1],[1,2],[1,2,2],[2],[2,2]]
</pre><p><strong>Example 2:</strong></p>
<pre><strong>Input:</strong> nums = [0]
<strong>Output:</strong> [[],[0]]
</pre>
<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10</code></li>
	<li><code>-10 &lt;= nums[i] &lt;= 10</code></li>
</ul>


**Companies**:  
[Apple](https://leetcode.com/company/apple), [Facebook](https://leetcode.com/company/facebook), [Amazon](https://leetcode.com/company/amazon), [Bloomberg](https://leetcode.com/company/bloomberg), [ByteDance](https://leetcode.com/company/bytedance)

**Related Topics**:  
[Array](https://leetcode.com/tag/array/), [Backtracking](https://leetcode.com/tag/backtracking/), [Bit Manipulation](https://leetcode.com/tag/bit-manipulation/)

**Similar Questions**:
* [Subsets (Medium)](https://leetcode.com/problems/subsets/)

## Video Notes


![vlcsnap-2022-07-10-09h46m48s408](https://user-images.githubusercontent.com/37560890/178131648-a555f9ec-a548-4883-b508-b3f85839dc20.png)
![vlcsnap-2022-07-10-09h46m50s444](https://user-images.githubusercontent.com/37560890/178131651-c07876e8-8069-4111-88da-c82e1208014a.png)
![vlcsnap-2022-07-10-09h48m01s138](https://user-images.githubusercontent.com/37560890/178131653-151409ab-e430-4097-814b-d24132cad19f.png)
![vlcsnap-2022-07-10-09h48m32s969](https://user-images.githubusercontent.com/37560890/178131655-561b8515-1b42-4abe-bbf7-bdb03f6f690f.png)
![vlcsnap-2022-07-10-09h56m58s550](https://user-images.githubusercontent.com/37560890/178131656-6fded1e3-97d6-4d99-85bd-183aecbe3713.png)
![vlcsnap-2022-07-10-09h57m59s934](https://user-images.githubusercontent.com/37560890/178131657-f0f90990-7c7d-47a5-b9d8-33da5f0aa6c9.png)
![vlcsnap-2022-07-10-09h59m47s097](https://user-images.githubusercontent.com/37560890/178131658-19b38b6c-a569-4173-a230-38203a85575e.png)
![vlcsnap-2022-07-10-10h01m28s798](https://user-images.githubusercontent.com/37560890/178131660-343d8860-6b4e-4053-a5d2-bec29f1f7b23.png)
![vlcsnap-2022-07-10-10h01m48s878](https://user-images.githubusercontent.com/37560890/178131662-00c9195d-b305-4cd4-8e5e-9c37333f88b2.png)
![vlcsnap-2022-07-10-10h06m13s604](https://user-images.githubusercontent.com/37560890/178131664-2e913985-6747-4dbf-aa83-3f5becb702bf.png)
![vlcsnap-2022-07-10-10h06m39s389](https://user-images.githubusercontent.com/37560890/178131665-2a84ba1a-5735-4f21-8553-6cb276c9504c.png)
![vlcsnap-2022-07-10-10h07m57s345](https://user-images.githubusercontent.com/37560890/178131666-684026a8-e2ae-4cfb-b7c4-b6faeac9ced4.png)
![vlcsnap-2022-07-10-10h08m32s443](https://user-images.githubusercontent.com/37560890/178131668-30894234-3e2b-4e10-80f1-86632ae6fba0.png)
![image](https://user-images.githubusercontent.com/37560890/178131808-f8cab6e1-6785-4036-a994-c8a4804b833c.png)

## Solution 1. Brute Force

There are at most `2^N` subsets in the `set`. Each insertion into the `set` takes `O(log(2^N) * N) = O(N^2)` time. So overall the time complexity is `O(2^N * N^2)`.

```cpp
// OJ: https://leetcode.com/problems/subsets-ii/
// Time: O(2^N * N^2)
// Space: O(2^N * N)

class Solution 
{
    set<vector<int>> s;
    vector<int> tmp;
    void dfs(vector<int> &A, int i) 
    {
        if (i == A.size()) 
	{
            s.insert(tmp);
            return;
        }
        dfs(A, i + 1);
        tmp.push_back(A[i]);
        dfs(A, i + 1);
        tmp.pop_back();
    }
public:
    vector<vector<int>> subsetsWithDup(vector<int>& A) 
    {
        sort(begin(A), end(A));
        dfs(A, 0);
        return vector<vector<int>>(begin(s), end(s));
    }
};
```

## Solution 2. Backtracking

There are at most `2^N` subsets in the `set`. Each insertion into the `set` takes `O(log(2^N) * N) = O(N^2)` time. So overall the time complexity is `O(2^N * N^2)`.

```cpp
// OJ: https://leetcode.com/problems/subsets-ii/
// Time: O(2^N * N^2)
// Space: O(2^N * N)

class Solution
{
public:
    
    void find_subsets(int index,vector<int> &nums,vector<int> &ds, vector<vector<int>> &ans)
    {
        // Add the generated combination to ans array as o/p
        ans.push_back(ds);
        
        // Generate all the possible subsets
        for(int i=index;i<nums.size();i++)
        {
            if(i!=index and nums[i]==nums[i-1]) continue;
            
            // Pick case
            ds.push_back(nums[i]);
            find_subsets(i+1,nums,ds,ans);
            
            // Not pick case
            ds.pop_back();
        }
        
    }
    
    vector<vector<int>> subsetsWithDup(vector<int>& nums) 
    {
        // Create the ans array
        vector<vector<int>> ans;
        
        // Create the temp vector
        vector<int> ds;
        
        // Sort the nums array
        sort(nums.begin(), nums.end());
        
        // Calling the method
        find_subsets(0,nums,ds,ans);
        
        // Finally return the ans
        return ans;
    }
};
```


