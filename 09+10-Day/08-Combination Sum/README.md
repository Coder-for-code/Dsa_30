# [39. Combination Sum (Medium)](https://leetcode.com/problems/combination-sum/)

<p>Given an array of <strong>distinct</strong> integers <code>candidates</code> and a target integer <code>target</code>, return <em>a list of all <strong>unique combinations</strong> of </em><code>candidates</code><em> where the chosen numbers sum to </em><code>target</code><em>.</em> You may return the combinations in <strong>any order</strong>.</p>

<p>The <strong>same</strong> number may be chosen from <code>candidates</code> an <strong>unlimited number of times</strong>. Two combinations are unique if the frequency of at least one of the chosen numbers is different.</p>

<p>It is <strong>guaranteed</strong> that the number of unique combinations that sum up to <code>target</code> is less than <code>150</code> combinations for the given input.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> candidates = [2,3,6,7], target = 7
<strong>Output:</strong> [[2,2,3],[7]]
<strong>Explanation:</strong>
2 and 3 are candidates, and 2 + 2 + 3 = 7. Note that 2 can be used multiple times.
7 is a candidate, and 7 = 7.
These are the only two combinations.
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> candidates = [2,3,5], target = 8
<strong>Output:</strong> [[2,2,2,2],[2,3,3],[3,5]]
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> candidates = [2], target = 1
<strong>Output:</strong> []
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= candidates.length &lt;= 30</code></li>
	<li><code>1 &lt;= candidates[i] &lt;= 200</code></li>
	<li>All elements of <code>candidates</code> are <strong>distinct</strong>.</li>
	<li><code>1 &lt;= target &lt;= 500</code></li>
</ul>


**Companies**:  
[Facebook](https://leetcode.com/company/facebook), [Amazon](https://leetcode.com/company/amazon), [Airbnb](https://leetcode.com/company/airbnb), [Microsoft](https://leetcode.com/company/microsoft), [Apple](https://leetcode.com/company/apple), [Snapchat](https://leetcode.com/company/snapchat), [Adobe](https://leetcode.com/company/adobe), [Goldman Sachs](https://leetcode.com/company/goldman-sachs), [Salesforce](https://leetcode.com/company/salesforce)

**Related Topics**:  
[Array](https://leetcode.com/tag/array/), [Backtracking](https://leetcode.com/tag/backtracking/)

**Similar Questions**:
* [Letter Combinations of a Phone Number (Medium)](https://leetcode.com/problems/letter-combinations-of-a-phone-number/)
* [Combination Sum II (Medium)](https://leetcode.com/problems/combination-sum-ii/)
* [Combinations (Medium)](https://leetcode.com/problems/combinations/)
* [Combination Sum III (Medium)](https://leetcode.com/problems/combination-sum-iii/)
* [Factor Combinations (Medium)](https://leetcode.com/problems/factor-combinations/)
* [Combination Sum IV (Medium)](https://leetcode.com/problems/combination-sum-iv/)

## Video Notes

![vlcsnap-2022-07-09-22h04m55s009](https://user-images.githubusercontent.com/37560890/178115557-c2c90cde-a956-41ba-8c9f-2980622068ab.png)
![vlcsnap-2022-07-09-22h06m15s011](https://user-images.githubusercontent.com/37560890/178115570-72d49e0e-2365-4088-b5ac-d49e16b434d5.png)
![vlcsnap-2022-07-09-22h06m33s370](https://user-images.githubusercontent.com/37560890/178115571-3f310b3f-4bff-4d3c-bb70-5d47ab0da572.png)
![vlcsnap-2022-07-09-22h09m46s163](https://user-images.githubusercontent.com/37560890/178115573-aeb813c8-3a7a-4a11-9d29-01d741e771b6.png)
![vlcsnap-2022-07-09-22h10m02s585](https://user-images.githubusercontent.com/37560890/178115590-77d184d4-27bc-4760-999d-69ef5708e48f.png)
![vlcsnap-2022-07-09-22h10m55s326](https://user-images.githubusercontent.com/37560890/178115592-df4e6814-632b-4944-a5f3-ad8506e4a573.png)
![vlcsnap-2022-07-09-22h11m22s794](https://user-images.githubusercontent.com/37560890/178115593-10ecaff1-fd72-4e8e-a956-8a9d13b4acae.png)
![vlcsnap-2022-07-09-22h11m46s857](https://user-images.githubusercontent.com/37560890/178115595-0a7618d0-adc1-472c-9edf-602bb5c059cf.png)
![vlcsnap-2022-07-09-22h12m05s718](https://user-images.githubusercontent.com/37560890/178115597-f03a267f-e9c8-4a62-be40-f8b3d15b7263.png)
![vlcsnap-2022-07-09-22h13m19s958](https://user-images.githubusercontent.com/37560890/178115598-e8a884a2-ad9d-485d-8ff4-5a0d5e9ab7e5.png)
![vlcsnap-2022-07-09-22h13m49s132](https://user-images.githubusercontent.com/37560890/178115600-5d27441d-c4aa-490f-a075-0ec4e9f1be76.png)
![vlcsnap-2022-07-09-22h14m24s712](https://user-images.githubusercontent.com/37560890/178115602-e52ffd2f-0ded-4247-9201-58bc536a28f2.png)
![vlcsnap-2022-07-09-22h14m56s730](https://user-images.githubusercontent.com/37560890/178115605-196331d4-adf5-4d77-b3f8-04e2dde42aa1.png)
![vlcsnap-2022-07-09-22h15m54s191](https://user-images.githubusercontent.com/37560890/178115609-9e101c39-71e0-41c9-a211-793f0253761d.png)
![image](https://user-images.githubusercontent.com/37560890/178115683-2f641ed3-a917-4531-8754-ed3a2e48faa1.png)
![image](https://user-images.githubusercontent.com/37560890/178115725-00278c2a-ae4c-449b-a502-60ccb2192902.png)


## Solution 1. Recursion

```cpp
Tc: O(2^n * k)
Sc: O(n) 

class Solution
{
public:
    
    // Helper find_combination method
    void find_combination(int index,int target,vector<int> &arr, 
                          vector<vector<int>> &ans, vector<int> &ds )
    {
        // Base case 
        if(index==arr.size())
        {
            if(target==0)
            {
                ans.push_back(ds);
            }
            return ;
        }
        
        // Pick the element
        if(arr[index] <= target)
        {
            ds.push_back(arr[index]);
            find_combination(index,target-arr[index],arr,ans,ds);
            ds.pop_back();
        }
        
        // Not pick case
        find_combination(index+1,target,arr,ans,ds);
        
    }
    
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) 
    {
        // Declare the ans vector for stroing all the combinations
        vector<vector<int>> ans;
        
        // Declare the datastructre which will be useful for passing to function
        vector<int> ds;
        
        // Calling the function
        find_combination(0,target,candidates,ans,ds);
        
        // Finally return the ans
        return ans;
    }
};

```
