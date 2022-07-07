# [740. Delete and Earn (Medium)](https://leetcode.com/problems/delete-and-earn/)

<p>You are given an integer array <code>nums</code>. You want to maximize the number of points you get by performing the following operation any number of times:</p>

<ul>
	<li>Pick any <code>nums[i]</code> and delete it to earn <code>nums[i]</code> points. Afterwards, you must delete <b>every</b> element equal to <code>nums[i] - 1</code> and <strong>every</strong> element equal to <code>nums[i] + 1</code>.</li>
</ul>

<p>Return <em>the <strong>maximum number of points</strong> you can earn by applying the above operation some number of times</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> nums = [3,4,2]
<strong>Output:</strong> 6
<strong>Explanation:</strong> You can perform the following operations:
- Delete 4 to earn 4 points. Consequently, 3 is also deleted. nums = [2].
- Delete 2 to earn 2 points. nums = [].
You earn a total of 6 points.
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> nums = [2,2,3,3,3,4]
<strong>Output:</strong> 9
<strong>Explanation:</strong> You can perform the following operations:
- Delete a 3 to earn 3 points. All 2's and 4's are also deleted. nums = [3,3].
- Delete a 3 again to earn 3 points. nums = [3].
- Delete a 3 once more to earn 3 points. nums = [].
You earn a total of 9 points.</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 2 * 10<sup>4</sup></code></li>
	<li><code>1 &lt;= nums[i] &lt;= 10<sup>4</sup></code></li>
</ul>


**Companies**:  
[Goldman Sachs](https://leetcode.com/company/goldman-sachs), [Amazon](https://leetcode.com/company/amazon), [Facebook](https://leetcode.com/company/facebook), [Bloomberg](https://leetcode.com/company/bloomberg)

**Related Topics**:  
[Array](https://leetcode.com/tag/array/), [Hash Table](https://leetcode.com/tag/hash-table/), [Dynamic Programming](https://leetcode.com/tag/dynamic-programming/)

**Similar Questions**:
* [House Robber (Medium)](https://leetcode.com/problems/house-robber/)

## Video Notes

![vlcsnap-2022-07-06-21h47m43s189](https://user-images.githubusercontent.com/37560890/177676340-74795ab6-24df-4930-bb71-c2bfbb74413d.png)
![vlcsnap-2022-07-06-21h50m48s882](https://user-images.githubusercontent.com/37560890/177676345-746f3bfd-75c8-4d7a-85d3-aa0513e5a6a7.png)
![vlcsnap-2022-07-06-21h51m06s287](https://user-images.githubusercontent.com/37560890/177676346-fa7b76c1-a6f2-4ecc-8f81-e3aba63df269.png)
![vlcsnap-2022-07-06-21h52m17s786](https://user-images.githubusercontent.com/37560890/177676348-a5512cee-91cb-419d-bd4e-43d1cf5331c1.png)
![vlcsnap-2022-07-06-21h52m46s299](https://user-images.githubusercontent.com/37560890/177676352-66883e58-3bf9-46ab-9d61-cd7bbb7bd0c8.png)
![vlcsnap-2022-07-06-21h53m16s601](https://user-images.githubusercontent.com/37560890/177676353-0c3670a8-c9d5-49a2-b344-84598d01d5fe.png)
![vlcsnap-2022-07-06-21h54m25s719](https://user-images.githubusercontent.com/37560890/177676356-2e92a680-3b18-473c-a739-55428d5eab95.png)
![vlcsnap-2022-07-06-21h54m56s457](https://user-images.githubusercontent.com/37560890/177676361-0b22b3ec-7c7e-45fa-8805-cf657aeb370c.png)
![vlcsnap-2022-07-06-21h55m23s062](https://user-images.githubusercontent.com/37560890/177676363-8a57beff-1d5b-4ac3-9e90-db95c0e59526.png)
![vlcsnap-2022-07-06-21h55m46s660](https://user-images.githubusercontent.com/37560890/177676364-c4c10e09-b8c4-4b80-aef6-42f88850ce68.png)
![vlcsnap-2022-07-06-21h57m57s234](https://user-images.githubusercontent.com/37560890/177676367-bfb5cfd6-8744-4921-8916-5a7a185d5876.png)
![vlcsnap-2022-07-06-21h58m21s845](https://user-images.githubusercontent.com/37560890/177676369-12388e2d-f3ef-4bc9-8b24-3d187548b9bf.png)
![image](https://user-images.githubusercontent.com/37560890/177677241-e11c7da4-71ce-40d0-b3c8-df14f9e8e15f.png)
![image](https://user-images.githubusercontent.com/37560890/177677608-0238ac24-e53b-4931-b7fc-f54be5221443.png)


## Solution 1. DP

```cpp
// OJ: https://leetcode.com/problems/delete-and-earn/
// Time: O(NlogN)
// Space: O(N)

class Solution 
{
public:
    int deleteAndEarn(vector<int>& nums) 
    {
        // Extract the maximum ele
        int maxi= *max_element(nums.begin(), nums.end());
        
        // Make a dp array
        int dp[20005];
        
        // Make the freq array
        vector<int> freq(20005);
        
        // Iterate on nums
        for(auto i: nums)
        {
            freq[i]++;
        }
        
        // Base 2 cases
        dp[1]= freq[1];
        dp[2]= max(dp[1], freq[2] *2);
        
        // Iterate from 3 to the maxi
        for(int i=3;i<=maxi;i++)
        {
            dp[i]= max(dp[i-1], dp[i-2]+ freq[i]*i);
        }
        
        // Finally return the maxi
        return dp[maxi];
        
    }
};
```

## Solution 2. DP

```cpp
// OJ: https://leetcode.com/problems/delete-and-earn/
// Time: O(N)
// Space: O(N)
class Solution 
{
public:
   int deleteAndEarn(vector<int>& nums) 
   {
        int n = 10001;
    
	//take the total sum by each number
        vector<int> sum(n, 0);
        vector<int> dp(n, 0);
    
        for(auto num: nums)
        {
            sum[num] += num;
        }
    
        dp[0] = 0;
        dp[1] = sum[1];
        //now apply the house robbing concept
        
       for(int i=2; i<n; i++)
       {
            dp[i] = max(dp[i-2] + sum[i], dp[i-1]);
       }
    
    return dp[n-1];
    }
};```

Or

```cpp
// OJ: https://leetcode.com/problems/delete-and-earn/
// Time: O(N)
// Space: O(N)

class Solution 
{
public:
    int deleteAndEarn(vector<int>& nums) 
    {
        int n = 10001;
        vector<int> values(n, 0);
        for (int num : nums)
            values[num] += num;

        int take = 0, skip = 0;
        for (int i = 0; i < n; i++) 
	{
            int takei = skip + values[i];
            int skipi = max(skip, take);
            take = takei;
            skip = skipi;
        }
        return max(take, skip);
    }
};```
