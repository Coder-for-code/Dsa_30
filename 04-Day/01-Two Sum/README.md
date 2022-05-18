1. https://leetcode.com/problems/two-sum/

![1](https://user-images.githubusercontent.com/37560890/168958946-f6121f02-6359-4fe5-8c02-29a256d0a3ca.jpg)

```cpp
Solution 1: Naive Approach (Brute Force)

Intuition: 
For each element, we try to find an element such that the sum of both elements is equal to the given target.

Approach:
We traverse through the array, and for each element i,
we try to find another element amongst the remaining elements, such that the sum of both the elements equals the target. 

vector<int> twoSum(vector<int>& nums, int target) 
{
    vector<int> res;
    for (int i = 0; i < nums.size(); ++i) 
    {
   	 for (int j = i + 1; j < nums.size(); ++j) 
	 {
   		 if (nums[i] + nums[j] == target) 
		 {
   			 res.emplace_back(i);
   			 res.emplace_back(j);
   			 break;
   		 }
   	 }
   	 if (res.size() == 2)
   		 break;
    }
    return res;
} 

Time Complexity: O(N2)
Space Complexity: O(1)
```
![image](https://user-images.githubusercontent.com/37560890/168959079-8c659623-ae7b-4dd1-a4ce-f4f93615832a.png)

```cpp

Solution 2: Two-Pointer Approach

Intuition:
Think about, what if the array is sorted? If the array is sorted, 
is it possible to reach a sum by traversing the array from both sides simultaneously?

We sort the array, use two variables, each will start from one end of the array
and traverse in both directions till we get the required sum.

Approach:
We traverse through the array, and for each element i, we try to 
find another element amongst the remaining elements, such that the sum of both the elements equals the target. 

vector<int> twoSum(vector<int>& nums, int target) 
{

    	vector<int> res,store;
    	store = nums;

    	sort(store.begin(), store.end());

    	int left=0,right=nums.size()-1;
    	int n1,n2;

    	while(left<right)
	{
        	if(store[left]+store[right]==target)
		{

            	n1 = store[left];
            	n2 = store[right];

            	break;

        	}
        	else if(store[left]+store[right]>target)
            	    right--;
        	else
            	    left++;
    	}

    	for(int i=0;i<nums.size();++i)
	{

        	if(nums[i]==n1)
            	    res.emplace_back(i);
        	else if(nums[i]==n2)
            	    res.emplace_back(i);
    	}

    	    return res;
	}

Time Complexity: O(NlogN)
Space Complexity: O(N)
```
![image](https://user-images.githubusercontent.com/37560890/168959381-d4ef3f34-39a0-4a72-bca0-6cca008ca6ed.png)


```cpp
Solution 3: Hashing (Most efficient)

Approach:
We can solve this problem efficiently by using hashing. 
We’ll use a hash-map to see if there’s a value target – i that 
can be added to the current array value i to get the sum equals to target. 
If target – i is found in the map, we return the current index, and index stored at target – nums[index] location in the map. 

This can be done in constant time.

vector<int> twoSum(vector<int>& nums, int target) 
{

    vector<int> res;
    unordered_map<int, int> mp;

    for (int i = 0; i < nums.size(); ++i) 
    {

   	 if (mp.find(target - nums[i]) != mp.end()) 
	 {

   		 res.emplace_back(i);
   		 res.emplace_back(mp[target - nums[i]]);
   		 return res;
   	 }

   	 mp[nums[i]] = i;
    }

    return res;
}

Time Complexity: O(N)
Space Complexity: O(N)
```
![image](https://user-images.githubusercontent.com/37560890/168959640-665d27bd-91c7-4e95-b8be-0658565b4898.png)
