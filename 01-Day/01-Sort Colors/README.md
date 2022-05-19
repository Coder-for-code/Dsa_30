1. https://leetcode.com/problems/sort-colors/

![1](https://user-images.githubusercontent.com/37560890/166398729-028b0bbe-e170-4d22-9e5d-b73dd14b35e8.jpg)
![image](https://user-images.githubusercontent.com/37560890/169198445-aa54a5af-7d3f-439a-9ac7-31be865a10f7.png)

```cpp
class Solution 
{
public:
    void sortColors(vector<int>& a) 
    {
        int low=0;
        int mid=0;
        int high= a.size()-1;
        
        while(mid<=high)
        {
            switch(a[mid])
            {
                case 0: 
                    swap(a[low++],a[mid++]) ; break;
                        
                case 1:
                    mid++; break;
                    
                case 2: 
                    swap(a[mid], a[high--]); break; 
            }
        }
    }
};
```
