# [198. House Robber (Medium)](https://leetcode.com/problems/house-robber/)

<p>You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security systems connected and <b>it will automatically contact the police if two adjacent houses were broken into on the same night</b>.</p>

<p>Given an integer array <code>nums</code> representing the amount of money of each house, return <em>the maximum amount of money you can rob tonight <b>without alerting the police</b></em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> nums = [1,2,3,1]
<strong>Output:</strong> 4
<strong>Explanation:</strong> Rob house 1 (money = 1) and then rob house 3 (money = 3).
Total amount you can rob = 1 + 3 = 4.
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> nums = [2,7,9,3,1]
<strong>Output:</strong> 12
<strong>Explanation:</strong> Rob house 1 (money = 2), rob house 3 (money = 9) and rob house 5 (money = 1).
Total amount you can rob = 2 + 9 + 1 = 12.
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 100</code></li>
	<li><code>0 &lt;= nums[i] &lt;= 400</code></li>
</ul>


**Companies**:  
[Amazon](https://leetcode.com/company/amazon), [Microsoft](https://leetcode.com/company/microsoft), [Google](https://leetcode.com/company/google), [Cisco](https://leetcode.com/company/cisco), [Apple](https://leetcode.com/company/apple), [Adobe](https://leetcode.com/company/adobe), [Qualtrics](https://leetcode.com/company/qualtrics), [Arcesium](https://leetcode.com/company/arcesium), [Bloomberg](https://leetcode.com/company/bloomberg), [Goldman Sachs](https://leetcode.com/company/goldman-sachs), [ByteDance](https://leetcode.com/company/bytedance), [eBay](https://leetcode.com/company/ebay), [Flipkart](https://leetcode.com/company/flipkart), [PayTM](https://leetcode.com/company/paytm)

**Related Topics**:  
[Array](https://leetcode.com/tag/array/), [Dynamic Programming](https://leetcode.com/tag/dynamic-programming/)

**Similar Questions**:
* [Maximum Product Subarray (Medium)](https://leetcode.com/problems/maximum-product-subarray/)
* [House Robber II (Medium)](https://leetcode.com/problems/house-robber-ii/)
* [Paint House (Medium)](https://leetcode.com/problems/paint-house/)
* [Paint Fence (Medium)](https://leetcode.com/problems/paint-fence/)
* [House Robber III (Medium)](https://leetcode.com/problems/house-robber-iii/)
* [Non-negative Integers without Consecutive Ones (Hard)](https://leetcode.com/problems/non-negative-integers-without-consecutive-ones/)
* [Coin Path (Hard)](https://leetcode.com/problems/coin-path/)
* [Delete and Earn (Medium)](https://leetcode.com/problems/delete-and-earn/)

## video Notes

![vlcsnap-2022-07-06-20h01m51s125](https://user-images.githubusercontent.com/37560890/177593796-21e40c7d-f11b-4e32-9ab2-c0e08e33829e.png)
![vlcsnap-2022-07-06-20h05m02s484](https://user-images.githubusercontent.com/37560890/177593806-765083b2-274a-4ed0-800b-c794a0e7d03e.png)
![vlcsnap-2022-07-06-20h05m52s967](https://user-images.githubusercontent.com/37560890/177593812-c668fdaa-2da2-45cf-be86-78df6bd1a7c3.png)
![vlcsnap-2022-07-06-20h06m15s297](https://user-images.githubusercontent.com/37560890/177593817-4ebbd5d7-b189-4fed-b448-8c3d556a424b.png)
![vlcsnap-2022-07-06-20h07m03s502](https://user-images.githubusercontent.com/37560890/177593821-663e2a44-a420-4672-bcc0-f2a94654ef76.png)
![vlcsnap-2022-07-06-20h07m38s508](https://user-images.githubusercontent.com/37560890/177593824-4fb53ab5-0b22-46ae-9bde-e401f32fc09b.png)
![vlcsnap-2022-07-06-21h17m48s693](https://user-images.githubusercontent.com/37560890/177593825-8519e09b-85f4-49fb-8916-ecddf2056f18.png)
![vlcsnap-2022-07-06-21h19m24s866](https://user-images.githubusercontent.com/37560890/177593827-60cd5019-d84f-46d3-9c73-e3690a880bae.png)
![vlcsnap-2022-07-06-21h21m07s833](https://user-images.githubusercontent.com/37560890/177593830-d84711a8-25fa-4a80-8169-d85ee8342e39.png)
![vlcsnap-2022-07-06-21h21m19s355](https://user-images.githubusercontent.com/37560890/177593833-af1be39c-ba9f-4051-9b9f-eed58ea8de1a.png)
![vlcsnap-2022-07-06-21h21m31s703](https://user-images.githubusercontent.com/37560890/177593836-5c0fe1ba-9712-47f1-a86f-4d01953ef999.png)
![vlcsnap-2022-07-06-21h22m27s951](https://user-images.githubusercontent.com/37560890/177593840-bca47ba6-3f79-4b7e-992b-42d6257938db.png)
![vlcsnap-2022-07-06-21h23m03s373](https://user-images.githubusercontent.com/37560890/177593843-4f09874a-5309-46cf-9540-1fa49402a68c.png)
![vlcsnap-2022-07-06-21h24m26s758](https://user-images.githubusercontent.com/37560890/177593849-de5bcea2-ba94-45d8-b136-749c26a000a0.png)
![vlcsnap-2022-07-06-21h25m00s199](https://user-images.githubusercontent.com/37560890/177593853-18089bda-4821-4fc0-8eb9-d4cf7355b7ea.png)
![vlcsnap-2022-07-06-21h25m43s139](https://user-images.githubusercontent.com/37560890/177593860-30c33b49-5f1c-49eb-8e82-218cdf73e102.png)
![vlcsnap-2022-07-06-21h26m10s121](https://user-images.githubusercontent.com/37560890/177593862-13fe2138-9c43-4a5e-9645-7c892299eef8.png)
![image](https://user-images.githubusercontent.com/37560890/177594171-89e6f899-dbd0-4308-b249-720d444f44fa.png)


## Solution 1. Recursion

```cpp
// OJ: https://leetcode.com/problems/house-robber/
// Author: github.com/lzl124631x
// Time: O(N)
// Space: O(N)

class Solution
{
public:
    int rob(vector<int>& A, int i = 0) 
    {
        return i < size(A) ? max(rob(A, i+1), A[i] + rob(A, i+2)) : 0;
    }
};
```
## Solution 2. DP Top down approach memoization

```cpp
// OJ: https://leetcode.com/problems/house-robber/
// Author: github.com/lzl124631x
// Time: O(N)
// Space: O(N)

class Solution 
{
public:
    
    int helper(int i, vector<int> &nums,int n,vector<int> &dp)
    {
        // Edge case handling
        if(i>=n) return 0;
        
        // Dp lookup table
        if(dp[i]!=-1) return dp[i];
        
        // Try both the pick and non pick cases
        int opt1= nums[i] + helper(i+2,nums,n,dp);
        int opt2= 0+ helper(i+1,nums,n,dp);
        
        // Store the solution i.e Memoization
        return dp[i]= max(opt1, opt2);
    }
    
    int rob(vector<int>& nums) 
    {
        // Compute the size of the nums size
        int n= nums.size();
        
        // Create the dp array and initialize with -1
        vector<int> dp(n+1,-1);
        
        // Calling the helper method
        return helper(0,nums,n,dp); 
    }
};
```

## Solution 3. Tabulation - Bottum up

```cpp
// OJ: https://leetcode.com/problems/house-robber/
// Author: github.com/lzl124631x
// Time: O(N)
// Space: O(N)

class Solution 
{
public:
    int rob(vector<int>& A) 
    {
        if(size(A) == 1) return A[0];
        vector<int> dp(A);
        dp[1] = max(A[0], A[1]);
    
    	for(int i = 2; i < size(A); i++)
            dp[i] = max(dp[i-1], A[i] + dp[i-2]);
        return dp.back();
    }
};
```

## Solution 4. Space optimization


```cpp
// OJ: https://leetcode.com/problems/house-robber/
// Author: github.com/lzl124631x
// Time: O(N)
// Space: O(1)

class Solution 
{
public:
    int rob(vector<int>& nums) 
    {
        int prev = 0, prev2 = 0;
        for (int n : nums) 
	{
            int cur = max(prev, prev2 + n);
            prev2 = prev;
            prev = cur;
        }
        return prev;
    }
};
```
