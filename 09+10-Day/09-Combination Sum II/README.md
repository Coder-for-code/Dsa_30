# [40. Combination Sum II (Medium)](https://leetcode.com/problems/combination-sum-ii/)

<p>Given a collection of candidate numbers (<code>candidates</code>) and a target number (<code>target</code>), find all unique combinations in <code>candidates</code>&nbsp;where the candidate numbers sums to <code>target</code>.</p>

<p>Each number in <code>candidates</code>&nbsp;may only be used <strong>once</strong> in the combination.</p>

<p><strong>Note:</strong></p>

<ul>
	<li>All numbers (including <code>target</code>) will be positive integers.</li>
	<li>The solution set must not contain duplicate combinations.</li>
</ul>

<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> candidates =&nbsp;<code>[10,1,2,7,6,1,5]</code>, target =&nbsp;<code>8</code>,
<strong>A solution set is:</strong>
[
  [1, 7],
  [1, 2, 5],
  [2, 6],
  [1, 1, 6]
]
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> candidates =&nbsp;[2,5,2,1,2], target =&nbsp;5,
<strong>A solution set is:</strong>
[
&nbsp; [1,2,2],
&nbsp; [5]
]
</pre>


**Related Topics**:  
[Array](https://leetcode.com/tag/array/), [Backtracking](https://leetcode.com/tag/backtracking/)

**Similar Questions**:
* [Combination Sum (Medium)](https://leetcode.com/problems/combination-sum/)

![vlcsnap-2022-07-09-22h35m25s056](https://user-images.githubusercontent.com/37560890/178129357-35c95acc-41b8-4aaf-85d4-32d3d63129c9.png)
![vlcsnap-2022-07-09-22h40m14s465](https://user-images.githubusercontent.com/37560890/178129359-6811bb42-ae0b-48ad-a5d3-0927ed55d55a.png)
![vlcsnap-2022-07-09-22h44m34s528](https://user-images.githubusercontent.com/37560890/178129360-d29576dc-e37d-4cfb-ae4c-f2ccf2ca3afb.png)
![vlcsnap-2022-07-09-22h44m56s452](https://user-images.githubusercontent.com/37560890/178129361-0107cdbe-ee42-4682-81ba-59a6c51576fa.png)
![vlcsnap-2022-07-09-22h45m18s553](https://user-images.githubusercontent.com/37560890/178129363-6d664b56-1f93-4eca-87e8-685cb54ca376.png)
![vlcsnap-2022-07-09-22h46m25s416](https://user-images.githubusercontent.com/37560890/178129364-e979caf5-40b2-4a8a-9737-3d3508a0909f.png)
![vlcsnap-2022-07-09-22h50m16s217](https://user-images.githubusercontent.com/37560890/178129365-1de21d0f-cf46-4701-83e8-2271f9346e39.png)
![vlcsnap-2022-07-09-22h51m43s981](https://user-images.githubusercontent.com/37560890/178129368-055f4a91-a32e-4cd7-aadb-8e1ab649d10b.png)
![vlcsnap-2022-07-09-22h53m12s251](https://user-images.githubusercontent.com/37560890/178129369-62ff47b4-fa1e-4b68-8748-36e6f9fb31d0.png)
![vlcsnap-2022-07-09-22h53m26s814](https://user-images.githubusercontent.com/37560890/178129371-df24c862-45a8-4bad-80b9-36aad9233099.png)
![vlcsnap-2022-07-09-22h54m11s060](https://user-images.githubusercontent.com/37560890/178129372-80b98bd6-b492-42c9-816c-b75de7f6a41b.png)
![vlcsnap-2022-07-09-22h55m07s724](https://user-images.githubusercontent.com/37560890/178129374-3eeef6c4-963e-472a-b7c7-5b91d2ef4f4a.png)
![vlcsnap-2022-07-09-22h56m02s521](https://user-images.githubusercontent.com/37560890/178129375-3ce0914a-7ee2-4537-b3d1-1cd4c9225487.png)
![vlcsnap-2022-07-09-22h56m52s915](https://user-images.githubusercontent.com/37560890/178129377-71a41be0-c3b3-4cfc-b0d7-e78f992f9b1a.png)
![vlcsnap-2022-07-09-22h57m00s986](https://user-images.githubusercontent.com/37560890/178129379-3a0809e6-e448-4fcf-9efe-9b934fae5810.png)
![vlcsnap-2022-07-09-22h58m41s311](https://user-images.githubusercontent.com/37560890/178129381-8214f83f-48b1-4e98-92c2-51397fc278de.png)
![vlcsnap-2022-07-09-22h59m08s121](https://user-images.githubusercontent.com/37560890/178129382-758a4019-3c56-42d7-b6e7-b36a8473e69e.png)
![vlcsnap-2022-07-09-22h59m27s906](https://user-images.githubusercontent.com/37560890/178129383-f6cac9e1-5b1b-4a70-a017-fe0bcb9e9ba3.png)
![vlcsnap-2022-07-09-22h59m49s260](https://user-images.githubusercontent.com/37560890/178129384-0a4075d5-c69e-4399-9a7b-0f483d92c833.png)
![vlcsnap-2022-07-09-23h00m15s916](https://user-images.githubusercontent.com/37560890/178129385-1d46f2e3-9add-43c3-aab7-528a9b293298.png)
![vlcsnap-2022-07-10-07h55m51s658](https://user-images.githubusercontent.com/37560890/178129389-9c98129d-1edc-4518-9597-dc3f5e8a7498.png)
![vlcsnap-2022-07-10-07h56m43s399](https://user-images.githubusercontent.com/37560890/178129390-839f93b6-ddd2-4c98-b3d1-37e5e5e7352b.png)
![vlcsnap-2022-07-10-07h57m24s677](https://user-images.githubusercontent.com/37560890/178129393-cdf5136c-4099-430f-a6ce-74c9b931629e.png)
![vlcsnap-2022-07-10-07h58m51s658](https://user-images.githubusercontent.com/37560890/178129394-1c7965df-0ff6-432f-b014-d3aecf6773ea.png)
![vlcsnap-2022-07-10-07h59m07s462](https://user-images.githubusercontent.com/37560890/178129395-2595ed3d-e21e-4d21-91ef-4e0923710ceb.png)


## Solution 1. DFS

```cpp
// OJ: https://leetcode.com/problems/combination-sum-ii/

// Time: O(N^2)
// Space: O(N)

class Solution 
{
    public: 
    void findCombination(int ind, int target, vector<int> &arr, vector<vector<int>> &ans, vector<int>&ds) 
    {
        // If the target is finally met then push into the ds
        if(target==0)
        {
            ans.push_back(ds);
            return;
        }        
         // Loop from i to n-1
        for(int i = ind;i<arr.size();i++) 
        {
             // Skip the duplicates elements
            if(i>ind && arr[i]==arr[i-1]) continue; 
        
            // If the element exceeds target then break 
            if(arr[i]>target) break; 
            
            // Pick case
            ds.push_back(arr[i]);
            
            // Move to the next element
            findCombination(i+1, target - arr[i], arr, ans, ds); 
            
            // Remove the element from the data structure
            ds.pop_back(); 
        }
    }
public:
    vector<vector<int>> combinationSum2(vector<int>& candidates, int target) 
    {
        
        // Sort the candidates array
        sort(candidates.begin(), candidates.end());
    
        // Create the ans vector
        vector<vector<int>> ans;
        
        // Make the temp datastructure
        vector<int> ds; 
        
         // Calling the find combi function
        findCombination(0, target, candidates, ans, ds);
        
        // Finally return the ans
        return ans; 
    }
};

```
