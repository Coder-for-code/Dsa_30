4. https://practice.geeksforgeeks.org/problems/largest-subarray-with-0-sum/1

![6](https://user-images.githubusercontent.com/37560890/168961444-f93a2251-b789-4f1c-aff8-5e9b9de6748e.jpg)
![7](https://user-images.githubusercontent.com/37560890/168961447-9e11120c-f8c1-4da4-97c9-3586365224ea.jpg)

```cpp
Solution 1 (Naive approach) :

Intuition:

We are required to find the longest subarray that sums to zero. 
So our initial approach could be to consider all possible subarrays of the given array
and check for the subarrays that sum to zero.
Among these valid subarrays (sum equal to zero) we’ll return the length of the largest subarray by maintaining a variable, say max.   

Approach :  

1. Initialise a variable max = 0, which stores length of longest subarray with sum 0.
2. Traverse the array from start and initialise a variable sum = 0 which stores sum of subarray starting with current index
3. Traverse from next element of current_index up to end of the array, each time add the element to sum and check if it is equal to 0.
4. If sum = 0, check if length of subarray so far is > max and if yes update max
5. Now keep adding elements and repeat step 3 a.
6. After the outer loop traverses all elements return max

Code:

import java.util.*;
public class Solution 
{
static int solve(int[] a)
{
	int  max = 0;
	for(int i = 0; i < a.length; ++i)
	{
		int sum = 0;
		for(int j = i; j < a.length; ++j)
		{
			sum += a[j];
			if(sum == 0){
				max = Math.max(max, j-i+1);
			}
		}
	}
	return max;
   }

    public static void main(String args[]) 
    { 
        int a[] = {9, -3, 3, -1, 6, -5};
        System.out.println(solve(a));
    } 
}

Time Complexity: O(N^2) as we have two loops for traversal
Space Complexity : O(1) as we aren’t using any extra space.
```

```cpp
Solution 2 (Optimised Approach) :

Intuition: 

Now let’s say we know that the sum of subarray(i, j) = S, 
and we also know that sum of subarray(i, x) = S where i < x < j.
We can conclude that the sum of subarray(x+1, j) = 0.

Let us understand the above statement clearly
So in this problem, we’ll store the prefix sum of every element, 
and if we observe that 2 elements have same prefix sum,
we can conclude that the 2nd part of this subarray sums to zero

Now let’s understand the approach

Approach: 

1. First let us initialise a variable say sum = 0 which stores the sum of elements traversed so far
and another variable say max = 0 which stores the length of longest subarray with sum zero.

2. Declare a HashMap<Integer, Integer> which stores the prefix sum of every element as key and its index as value.

3. Now traverse the array, and add the array element to our sum. 

(i)  If sum = 0, then we can say that the subarray until the current index has a sum = 0,      so we update max with the maximum value of (max, current_index+1)
(ii)  If sum is not equal to zero then we check hashmap if we’ve seen a subarray with this sum before
if HashMap contains sum -> this is where the above-discussed case occurs (subarray with equal sum), so we update our max 
else -> Insert (sum, current_index) into hashmap to store prefix sum until current index

4. After traversing the entire array our max variable has the length of longest substring having sum equal to zero, so return max.

NOTE : we do not update the index of a sum if it’s seen again because we require the length of the longest subarray

int maxLen(int A[], int n)
{
    // Your code here
    unordered_map<int,int> mpp; 
    int maxi = 0;
    int sum = 0; 
    
    for(int i = 0;i<n;i++) 
    {
        sum += A[i]; 
        if(sum == 0) 
	{
            maxi = i + 1; 
        }
        
	else 
	{
            if(mpp.find(sum) != mpp.end()) 
	    {
                maxi = max(maxi, i - mpp[sum]); 
            }
            
	    else 
	    {
                mpp[sum] = i;
            }
        }   
    }

    return maxi; 
}

Time Complexity: O(N), as we are traversing the array only once
Space Complexity: O(N), in the worst case we would insert all array elements prefix sum into our hashmap
```
![image](https://user-images.githubusercontent.com/37560890/168961833-5c4addb8-a41c-47ca-bba8-bb6107835337.png)
