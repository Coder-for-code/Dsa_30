3. https://leetcode.com/problems/majority-element/

![5](https://user-images.githubusercontent.com/37560890/168952167-04b0c77c-0db2-451a-801f-9eadf57a1d99.jpg)

```cpp
Solution 1 (Brute Force):

1. Check the count of occurrences of all elements of the array one by one. 
2. Start from the first element of the array and count the number of times it occurs in the array. 
3. If the count is greater than the floor of N/2 then return that element as the answer. 
4. If not, proceed with the next element in the array and repeat the process.

Time Complexity: O(N2) 
Space Complexity: O(1)


```

```cpp
Solution 2 (Better):

Intuition: 

Use a better data structure to reduce the number of look up operations and hence the time complexity. 
Moreover, we have been calculating the count of the same element again and again – so we have to reduce that also.

Approach: 

1. Use a hashmap and store as (key,value) pairs. (Can also use frequency array based on size of nums) 
2. Here the key will be the element of the array and value will be the number of times it occurs. 
3. Traverse the array and update the value of the key. Simultaneously check if the value is greater than floor of N/2. 
4. If yes, return the key 
5. Else iterate forward.

Time Complexity: O(N)-> Frequency array or O(N log N) -> HashMap 
Space Complexity: O(N)



```


```cpp
Solution 3 (Optimal): Moore’s Voting Algorithm

Intuition: 

The question clearly states that the nums array has a majority element. 
Since it has a majority element we can say definitely the count is more than N/2.

Majority element count = N/2 + x;
Minority/Other elements = N/2 – x;

Where x is the number of times it occurs after reaching the minimum value N/2.

Now, we can say that count of minority elements and majority element are equal 
upto certain point of time in the array. 
So when we traverse through the array we try to keep track of the count of elements and which element we are tracking.
Since the majority element appears more than N/2 times, we can say that at 
some point in array traversal we find the majority element. 

Approach: 

1. Initialize 2 variables: 
2. Count –  for tracking the count of element
3. Element – for which element we are counting
4. Traverse through nums array.
5. If Count is 0 then initialize the current traversing integer of array as Element 
6. If the traversing integer of array and Element are same increase Count by 1
7. If they are different decrease Count by 1
8. The integer present in Element is the result we are expecting 

class Solution
{
public:
    int majorityElement(vector<int>& nums) 
    {
        int count = 0;
        int candidate = 0;
	
	for (int num : nums) 
	{
            if (count == 0) 
	    {
                candidate = num;
            }
            
	    if(num==candidate) count += 1; 
            else count -= 1; 
        }

        return candidate;
    }
};

Time Complexity: O(N)
Space Complexity: O(1)

Follow-up question you can try: Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.
```
