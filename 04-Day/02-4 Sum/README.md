2. https://leetcode.com/problems/4sum/

![1](https://user-images.githubusercontent.com/37560890/168969273-62916832-6776-4b7b-a51c-4a199df6698d.jpg)
![2](https://user-images.githubusercontent.com/37560890/168969290-07fd8d9a-d8b1-467b-96ff-9b49eb1918ff.jpg)

```cpp
Solution 1: Using 3 pointers and Binary Search

Approach:

The main idea is to sort the array, and then we can think of searching in the array using the binary search technique.

Since we need the 4 numbers which sum up to target.

So we will fix three numbers as nums[i], nums[j] and nums[k], and search for
the remaining (target – (nums[i] + nums[j] + nums[k])) in the array.

Since we sorted the array during the start, we can apply binary search to search for this value,
and if it occurs we can store them. In order to get the unique quads, we use a set data structure to store them.

#include<bits/stdc++.h>
using namespace std;
class Solution 
{
public:
    vector<vector<int>> fourSum(vector<int>& nums, int target) 
    {
        int n = nums.size();
        
        sort(nums.begin(),nums.end());
      
       set<vector<int>> sv;
        for(int i=0;i<n;i++)
        {
            for(int j=i+1;j<n;j++)
            {
    
                for(int k=j+1;k<n;k++)
                { 
                  
                   int x = (long long)target - 
                           (long long)nums[i]-
                           (long long)nums[j]-(long long)nums[k];
                   
                        if(binary_search(nums.begin()+k+1,nums.end(),x))
			{
                            vector<int> v;
                            v.push_back(nums[i]);
                            v.push_back(nums[j]);
                            v.push_back(nums[k]);
                            v.push_back(x);
                            sort(v.begin(),v.end());
                            sv.insert(v);
                        }
                }
            }
        }
        vector<vector<int>> res(sv.begin(),sv.end());
        return res;
    }
};
int main()
{
    Solution obj;
    vector<int> v{1,0,-1,0,-2,2};
    
    vector<vector<int>> sum=obj.fourSum(v,0);
    cout<<"The unique quadruplets are"<<endl;
    
    for (int i = 0; i < sum.size(); i++)
    {
        for (int j = 0; j < sum[i].size(); j++)
            cout << sum[i][j] << " ";
        cout << endl;
    }
}

Time Complexity: O(N log N + N³ logN)
Reason: Sorting the array takes N log N and three nested loops will be taking N³ and 
for binary search, it takes another log N.

Space Complexity: O(M * 4), where M is the number of quads


```

```cpp
Solution 2: Optimized Approach

Intuition: 

In the previous approach we fixed three-pointers and did a binary search to find the fourth. 
Over here we will fix two-pointers and then find the remaining two elements using two pointer technique as the array will be sorted at first.

Approach: 

Sort the array, and then fix two pointers, so the remaining sum will be (target – (nums[i] + nums[j])). 

Now we can fix two pointers, one front, and another back, and easily use 
a two-pointer to find the remaining two numbers of the quad. In order to avoid duplications
we jump the duplicates, because taking duplicates will result in repeating quads. 

We can easily jump duplicates, by skipping the same elements by running a loop.

Code:

#include<bits/stdc++.h>
using namespace std;

class Solution 
{
public:
    vector<vector<int>> fourSum(vector<int>& num, int target) 
    {
         vector<vector<int> > res;
        
        if (num.empty())
            return res;
        int n = num.size(); 
        sort(num.begin(),num.end());
    
        for (int i = 0; i < n; i++) 
	{
        
            int target_3 = target - num[i];
        
            for (int j = i + 1; j < n; j++) 
	    {
            
                int target_2 = target_3 - num[j];
            
                int front = j + 1;
                int back = n - 1;
            
                while(front < back) 
		{
                
                    int two_sum = num[front] + num[back];
                
                    if (two_sum < target_2) front++;
                
                    else if (two_sum > target_2) back--;
                
                    else 
		    {
                    
                        vector<int> quadruplet(4, 0);
                        quadruplet[0] = num[i];
                        quadruplet[1] = num[j];
                        quadruplet[2] = num[front];
                        quadruplet[3] = num[back];
                        res.push_back(quadruplet);
                    
                        // Processing the duplicates of number 3
                        while (front < back && num[front] == quadruplet[2]) ++front;
                    
                        // Processing the duplicates of number 4
                        while (front < back && num[back] == quadruplet[3]) --back;
                
                    }
                }
                
                // Processing the duplicates of number 2
                while(j + 1 < n && num[j + 1] == num[j]) ++j;
            }
        
            // Processing the duplicates of number 1
            while (i + 1 < n && num[i + 1] == num[i]) ++i;
        
        }
    
        return res;
    }
};

int main()
{
    Solution obj;
    vector<int> v{1,0,-1,0,-2,2};
    
    vector<vector<int>> sum=obj.fourSum(v,0);
    cout<<"The unique quadruplets are"<<endl;
    for (int i = 0; i < sum.size(); i++) {
        for (int j = 0; j < sum[i].size(); j++)
            cout << sum[i][j] << " ";
        cout << endl;
    }
}


```
![image](https://user-images.githubusercontent.com/37560890/168969431-71ab41d5-a3cc-49be-bdff-f25b697d9a59.png)

