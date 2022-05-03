5. https://leetcode.com/problems/maximum-subarray/

![3](https://user-images.githubusercontent.com/37560890/166399579-c2f42f6f-1104-4a0a-8f98-64ad47fb51a7.jpg)

```cpp

class Solution 
{
public:
    int maxSubArray(vector<int>& nums)
    {
        int n = nums.size();
        int maxi = INT_MIN, sum = 0;
        
        for(int i=0;i<n;i++)
        {
            sum += nums[i];
            maxi = max(sum,maxi);
            
            if(sum<0) sum = 0;
        }
        
        return maxi;
    }
};
```
