# [46. Permutations (Medium)](https://leetcode.com/problems/permutations/)

<p>Given a collection of <strong>distinct</strong> integers, return all possible permutations.</p>

<p><strong>Example:</strong></p>

<pre><strong>Input:</strong> [1,2,3]
<strong>Output:</strong>
[
  [1,2,3],
  [1,3,2],
  [2,1,3],
  [2,3,1],
  [3,1,2],
  [3,2,1]
]
</pre>


**Related Topics**:  
[Backtracking](https://leetcode.com/tag/backtracking/)

**Similar Questions**:
* [Next Permutation (Medium)](https://leetcode.com/problems/next-permutation/)
* [Permutations II (Medium)](https://leetcode.com/problems/permutations-ii/)
* [Permutation Sequence (Medium)](https://leetcode.com/problems/permutation-sequence/)
* [Combinations (Medium)](https://leetcode.com/problems/combinations/)

## Video Notes

![vlcsnap-2022-07-10-10h27m45s798](https://user-images.githubusercontent.com/106215989/178134708-432908e4-b00f-4bf3-91c8-708c3eaabe64.png)
![vlcsnap-2022-07-10-10h28m03s545](https://user-images.githubusercontent.com/106215989/178134714-e3428808-668e-427a-b256-900cc9a39a3c.png)
![vlcsnap-2022-07-10-10h37m40s104](https://user-images.githubusercontent.com/106215989/178134715-7488d98d-a89a-4099-b5dc-4c487aca2eca.png)
![vlcsnap-2022-07-10-10h38m19s612](https://user-images.githubusercontent.com/106215989/178134717-af816df5-eaa1-470a-a69b-2c9c8d50f164.png)
![vlcsnap-2022-07-10-10h40m01s273](https://user-images.githubusercontent.com/106215989/178134719-92e10891-867a-4723-ba8c-ba7c37e1bdf5.png)
![vlcsnap-2022-07-10-10h41m31s275](https://user-images.githubusercontent.com/106215989/178134721-f572eccd-1bdd-406b-aee0-2d45eb383511.png)
![vlcsnap-2022-07-10-10h42m35s033](https://user-images.githubusercontent.com/106215989/178134723-65c5aa2b-f1c6-4bf9-aa1c-0ec0f6bf9e28.png)
![vlcsnap-2022-07-10-10h45m03s088](https://user-images.githubusercontent.com/106215989/178134736-6b23f56b-3589-4459-a05d-72da2142b4fc.png)
![vlcsnap-2022-07-10-10h45m50s438](https://user-images.githubusercontent.com/106215989/178134737-574af54c-9364-45d6-9a78-033cb5f2185d.png)
![vlcsnap-2022-07-10-10h46m11s993](https://user-images.githubusercontent.com/106215989/178134739-7d327993-255b-4be3-8ef3-9839d9797dbe.png)
![vlcsnap-2022-07-10-10h46m22s768](https://user-images.githubusercontent.com/106215989/178134740-825fdb88-4f85-413a-9638-d4e1303b0ee1.png)
![image](https://user-images.githubusercontent.com/37560890/178135049-b366fcc3-5d60-4cae-9c4f-bf5ec579d5e8.png)
![image](https://user-images.githubusercontent.com/37560890/178135059-359d28d9-e185-4f1a-af82-d63961e7abd7.png)

## Solution 1. Backtracking

```cpp
// OJ: https://leetcode.com/problems/permutations/
// Time: O(N!)
// Space: O(N)

class Solution 
{
public:
    
    void recursive_permute(vector<int> &ds,vector<int> &nums,vector<vector<int>> &ans,int visited[])
    {
        // Base case
        if(ds.size()== nums.size())
        {
            ans.push_back(ds);
            return ;
        }
        
        // Try out all the possible permutations
        for(int i=0; i<nums.size();i++)
        {
            // If not marked then decide to pick that element
            if(!visited[i])
            {
                ds.push_back(nums[i]);
                visited[i] =1;
                recursive_permute(ds,nums,ans,visited);
                
                // While returning back unmark that element
                visited[i] = 0;
                ds.pop_back();
            }
        }
        
    }
    
    vector<vector<int>> permute(vector<int>& nums) 
    {
        // Create the ans vector for the o/p
        vector<vector<int>> ans;
        
        // Create the temp ds
        vector<int> ds;
        
        // Create the visited array to keep the markup
        int visited[nums.size()];
        
        // Make all the visited array to 0
        for(int i=0;i<nums.size();i++)
        {
            visited[i]=0;
        }
        
        // Call therecursive function
        recursive_permute(ds,nums,ans,visited);
        
        // Return the ans finally
        return ans;
    }
};
```
