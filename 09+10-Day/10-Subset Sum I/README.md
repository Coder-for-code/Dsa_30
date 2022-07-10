# [78. Subsets (Medium)](https://leetcode.com/problems/subsets/)

<p>Given an integer array <code>nums</code> of <strong>unique</strong> elements, return <em>all possible subsets (the power set)</em>.</p>

<p>The solution set <strong>must not</strong> contain duplicate subsets. Return the solution in <strong>any order</strong>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> nums = [1,2,3]
<strong>Output:</strong> [[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> nums = [0]
<strong>Output:</strong> [[],[0]]
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10</code></li>
	<li><code>-10 &lt;= nums[i] &lt;= 10</code></li>
	<li>All the numbers of&nbsp;<code>nums</code> are <strong>unique</strong>.</li>
</ul>


**Companies**:  
[Facebook](https://leetcode.com/company/facebook), [Amazon](https://leetcode.com/company/amazon), [Google](https://leetcode.com/company/google), [Twitter](https://leetcode.com/company/twitter), [Bloomberg](https://leetcode.com/company/bloomberg), [Goldman Sachs](https://leetcode.com/company/goldman-sachs), [Paypal](https://leetcode.com/company/paypal)

**Related Topics**:  
[Array](https://leetcode.com/tag/array/), [Backtracking](https://leetcode.com/tag/backtracking/), [Bit Manipulation](https://leetcode.com/tag/bit-manipulation/)

**Similar Questions**:
* [Subsets II (Medium)](https://leetcode.com/problems/subsets-ii/)
* [Generalized Abbreviation (Medium)](https://leetcode.com/problems/generalized-abbreviation/)
* [Letter Case Permutation (Medium)](https://leetcode.com/problems/letter-case-permutation/)
* [Find Array Given Subset Sums (Hard)](https://leetcode.com/problems/find-array-given-subset-sums/)
* [Count Number of Maximum Bitwise-OR Subsets (Medium)](https://leetcode.com/problems/count-number-of-maximum-bitwise-or-subsets/)

## Video Notes

![vlcsnap-2022-07-10-09h09m36s019](https://user-images.githubusercontent.com/37560890/178130829-702c12ad-5ca5-4552-a083-d491c8cd4f55.png)
![vlcsnap-2022-07-10-09h09m42s088](https://user-images.githubusercontent.com/37560890/178130832-b1981827-712c-4cc2-b928-f84e7123a948.png)
![vlcsnap-2022-07-10-09h13m43s503](https://user-images.githubusercontent.com/37560890/178130833-e9e129a5-1339-47e0-825b-2d4162fb5e77.png)
![vlcsnap-2022-07-10-09h13m51s112](https://user-images.githubusercontent.com/37560890/178130834-9b034b6e-8f5d-406b-8fad-bdf329454e0e.png)
![vlcsnap-2022-07-10-09h14m09s293](https://user-images.githubusercontent.com/37560890/178130835-7d3027ed-8a6b-4dc5-b834-a3e8bf581e4b.png)
![vlcsnap-2022-07-10-09h14m16s949](https://user-images.githubusercontent.com/37560890/178130836-18312dc3-8d16-42e9-9733-82bec37d07a5.png)
![vlcsnap-2022-07-10-09h14m21s716](https://user-images.githubusercontent.com/37560890/178130837-59d5f6dc-f918-4174-bc82-be57846148f3.png)
![vlcsnap-2022-07-10-09h14m53s740](https://user-images.githubusercontent.com/37560890/178130838-bbd68a53-08cf-4d69-905f-a79a835e8ab4.png)
![vlcsnap-2022-07-10-09h16m04s869](https://user-images.githubusercontent.com/37560890/178130840-41a6d1f8-9013-4c4d-ae81-b7dc96fc0d28.png)
![vlcsnap-2022-07-10-09h18m11s391](https://user-images.githubusercontent.com/37560890/178130841-db41f1a3-a9b7-40d2-ac96-df8669584b0a.png)
![vlcsnap-2022-07-10-09h22m40s316](https://user-images.githubusercontent.com/37560890/178130843-357b829f-ad6e-45b1-a85e-c2f50b96f212.png)
![vlcsnap-2022-07-10-09h23m13s862](https://user-images.githubusercontent.com/37560890/178130844-060df412-8ab3-43b9-bf8b-87697eda19de.png)
![vlcsnap-2022-07-10-09h23m27s656](https://user-images.githubusercontent.com/37560890/178130845-5c00bf14-35c8-427f-bf85-b685e7740ac0.png)
![vlcsnap-2022-07-10-09h24m00s768](https://user-images.githubusercontent.com/37560890/178130846-d53a14ab-3345-4d33-bdb8-4ad1824efa35.png)
![vlcsnap-2022-07-10-09h24m35s065](https://user-images.githubusercontent.com/37560890/178130847-42b957b4-870e-49c1-918e-0762e62561a3.png)
![vlcsnap-2022-07-10-09h24m54s550](https://user-images.githubusercontent.com/37560890/178130848-5c6628ab-5a49-4c3c-830a-1a9394c3c4ca.png)
![vlcsnap-2022-07-10-09h25m43s475](https://user-images.githubusercontent.com/37560890/178130850-0edbc23b-f111-43d1-a586-c82df7c23ae9.png)
![vlcsnap-2022-07-10-09h26m13s779](https://user-images.githubusercontent.com/37560890/178130852-1afe0179-6b7a-4ce0-9164-1bfbc13dc935.png)
![vlcsnap-2022-07-10-09h26m32s361](https://user-images.githubusercontent.com/37560890/178130854-587a14c3-614e-42cf-a5e0-60a3390999e0.png)
![vlcsnap-2022-07-10-09h26m44s442](https://user-images.githubusercontent.com/37560890/178130855-61d3d9b3-52e2-4c68-9248-59ae9aa55cd6.png)
![vlcsnap-2022-07-10-09h27m15s190](https://user-images.githubusercontent.com/37560890/178130870-23efb26d-6aef-4859-ae17-6cc7ee3e9c8a.png)
![vlcsnap-2022-07-10-09h27m28s025](https://user-images.githubusercontent.com/37560890/178130873-e5185d3a-f855-4843-b2cd-68ae0f3ba1d0.png)
![vlcsnap-2022-07-10-09h28m12s886](https://user-images.githubusercontent.com/37560890/178130875-325993d0-0749-4dbc-b956-7ae884b1c8d1.png)
![vlcsnap-2022-07-10-09h28m24s665](https://user-images.githubusercontent.com/37560890/178130876-6f287696-a5d2-483a-8400-b3a9dbbc26c5.png)
![vlcsnap-2022-07-10-09h29m07s506](https://user-images.githubusercontent.com/37560890/178130879-f28ae509-c872-45a0-a3e4-3198b6d82d53.png)
![vlcsnap-2022-07-10-09h29m41s072](https://user-images.githubusercontent.com/37560890/178130884-06283bb3-2651-47bb-bbeb-18db0c037186.png)
![image](https://user-images.githubusercontent.com/37560890/178130934-44ed13dd-a899-4329-ac1f-799062a3558a.png)
![image](https://user-images.githubusercontent.com/37560890/178130949-2b563b76-9fb6-474a-bb50-be0be688f09f.png)


## Solution 1. Backtracking

```cpp
// OJ: https://leetcode.com/problems/subsets/
// Recursive Solution
// Time complexity : O(N*(2^N))
// Space complexity : O(N*(2^N))

class Solution 
{
public:
    
    // Create the ans vector
    vector<vector<int>> ans;
    
    // Helper method
    void sub(vector<int> &nums, int i, vector<int> temp)
    {
        // Base case
        if(i==nums.size())
        {
            ans.push_back(temp);
            return;
        }
        
        // Pick case
        sub(nums, i+1, temp);
        temp.push_back(nums[i]);
        
        // Non pick case
        sub(nums, i+1, temp);
    }
    
    vector<vector<int>> subsets(vector<int>& nums)
    {
        // Temp vctor
        vector<int> temp;       
        
        // Calling the method
        sub(nums, 0, temp); // or sub(nums, 0, vector<int> {});
        
        // Finally return the ans 
        return ans;
    }
};
```
