
## Solution 1. Recursion Code

```cpp
Tc: O(2^n)
Sc: O(n) + O(n)

// Helper method
int f(int index, vector<int> &nums)
{
    // If index==0 then return the nums[index]
    if(index==0) return nums[index];

    // If index < 0 then return 0
    if(index<0) return 0;
    
    // pick and not pick logic
    int p = nums[index] + f(index-2, nums);
    int np = 0+ f(index-1,nums);
    
    // Finally return the max of pick and non pick
    return max(p ,np);    
}

int maximumNonAdjacentSum(vector<int> &nums)
{
    // Compute the size of array
    int n= nums.size();
    
    // Calling the helper method
    return f(n-1, nums);
    
}
```

## Solution 2. Memoization

```cpp
Tc: O(n)
Sc: O(n) + O(n)

// Helper method
int f(int index, vector<int> &nums, vector<int> &dp) 
{
    // If index==0 then return the nums[index]
    if(index==0) return nums[index];

    // Lookup 
    if(dp[index] != -1) return dp[index];
    
    // If index < 0 then return 0
    if(index<0) return 0;
    
    // pick and not pick logic
    int p = nums[index] + f(index-2, nums,dp);
    int np = 0+ f(index-1,nums,dp);
    
    // Finally return the max of pick and non pick
    return dp[index]= max(p ,np);    
}

int maximumNonAdjacentSum(vector<int> &nums)
{
    // Compute the size of array
    int n= nums.size();
    
    // Create the dp array
    vector<int> dp(n,-1);    
    
    // Calling the helper method
    return f(n-1, nums,dp);
    
}
```
