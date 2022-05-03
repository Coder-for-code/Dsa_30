3. https://leetcode.com/problems/next-permutation/

![5 1](https://user-images.githubusercontent.com/37560890/166399395-8da777fc-4558-4c13-a10e-61135b2869cd.jpg)
![5](https://user-images.githubusercontent.com/37560890/166399413-4fd72127-759c-4495-8da4-d273676345bd.jpg)

``` cpp
class Solution
{
public:
    void nextPermutation(vector<int>& nums) 
    {
    	int n = nums.size(), k, l;
        for (k = n - 2; k >= 0; k--) 
        {
            if (nums[k] < nums[k + 1]) 
            {
                break;
            }
        }
    	if (k < 0)    reverse(nums.begin(), nums.end());
        else 
        {
    	    for (l = n - 1; l > k; l--) {
                if (nums[l] > nums[k]) {
                    break;
                }
            } 
    	    swap(nums[k], nums[l]);
    	    reverse(nums.begin() + k + 1, nums.end());
        }
    }
};
```
