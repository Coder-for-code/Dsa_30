2. https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

![2](https://user-images.githubusercontent.com/37560890/166399153-bf82e98e-6837-4817-8773-da1a4a5ed64e.jpg)

```cpp
class Solution
{
public:
    int maxProfit(vector<int>& prices) 
    {
        int min_p= INT_MAX ;
        int profit=0;
        
        for(int i=0;i<prices.size();i++)
        {
            min_p= min(min_p, prices[i]);
            profit= max(profit, prices[i]- min_p);
        }
        return profit;
        
    }
};
```
