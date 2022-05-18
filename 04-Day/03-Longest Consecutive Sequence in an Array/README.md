3. https://leetcode.com/problems/longest-consecutive-sequence/

![4](https://user-images.githubusercontent.com/37560890/168961006-08c09c3f-ad06-4a6c-b6f3-9e9f1c87fc0e.jpg)
![5](https://user-images.githubusercontent.com/37560890/168961014-17459a30-3cde-4e64-9c73-ce537b1a92ec.jpg)

```cpp
Solution 1: (Brute force)
Approach: We can simply sort the array and run a for loop to find the longest consecutive sequence.

Code:

#include<bits/stdc++.h>
using namespace std;

int longestConsecutive(vector<int> nums) 
{
        if(nums.size() == 0 )
	{
            return 0;
        }
        
        sort(nums.begin(),nums.end());
        
        int ans = 1;
        int prev = nums[0];
        int cur = 1;
        
        for(int i = 1;i < nums.size();i++)
	{
            if(nums[i] == prev+1)
	    {
                cur++;
            }
            
	    else if(nums[i] != prev)
	    {
                cur = 1;
            }
            
	    prev = nums[i];
            ans = max(ans, cur);
        }
        return ans;
    }
    int main()
    {
        vector<int> arr{100,200,1,2,3,4};
        int lon=longestConsecutive(arr);
        cout<<"The longest consecutive sequence is "<<lon<<endl;
        
    }

Time Complexity: We are first sorting the array which will take O(N * log(N)) time and 
then we are running a for loop which will take O(N) time. Hence, the overall time complexity will be O(N * log(N)).

Space Complexity: The space complexity for the above approach is O(1) because we are not using any auxiliary space

```

```cpp
Solution 2: (Optimal Approach)

Approach: 
We will first push all are elements in the HashSet. 
Then we will run a for loop and check for any number(x) if it is
the starting number of the consecutive sequence by checking if the HashSet contains (x-1) or not.
If ‘x’ is the starting number of the consecutive sequence we will keep searching for the numbers y = x+1, x+2, x+3, …..
And stop at the first ‘y’ which is not present in the HashSet.
Using this we can calculate the length of the longest consecutive subsequence. 

Code:

#include<bits/stdc++.h>
using namespace std;

int longestConsecutive(vector < int > & nums) 
{
  set < int > hashSet;
  for (int num: nums) 
  {
    hashSet.insert(num);
  }

  int longestStreak = 0;

  for (int num: nums) 
  {
    if (!hashSet.count(num - 1)) 
    {
      int currentNum = num;
      int currentStreak = 1;

      while (hashSet.count(currentNum + 1)) 
      {
        currentNum += 1;
        currentStreak += 1;
      }

      longestStreak = max(longestStreak, currentStreak);
    }
  }

  return longestStreak;
}

int main()
{
  vector<int> arr{100,200,1,2,3,4};
  int lon = longestConsecutive(arr);
  cout << "The longest consecutive sequence is " << lon << endl;

}

Time Complexity: The time complexity of the above approach is O(N) 
because we traverse each consecutive subsequence only once.

Space Complexity: The space complexity of the above approach is O(N) 
because we are maintaining a HashSet.
```
