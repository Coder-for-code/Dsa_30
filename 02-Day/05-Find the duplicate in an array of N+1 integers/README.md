5. https://leetcode.com/problems/find-the-duplicate-number/


![5 1](https://user-images.githubusercontent.com/37560890/166862838-d617dd4e-73cd-410c-8273-99311af8ea82.jpg)
![5](https://user-images.githubusercontent.com/37560890/166862843-6e16d396-c11a-4c13-b2d1-599daf4fd402.jpg)

Solution 1:Using sorting

```cpp
#include<bits/stdc++.h>

using namespace std;
int findDuplicate(vector < int > & arr) 
{
  int n = arr.size();
  sort(arr.begin(), arr.end());

  for (int i = 0; i < n - 1; i++) 
  {
    if (arr[i] == arr[i + 1]) 
    {
      return arr[i];
    }
  }
}

int main() 
{
  vector < int > arr;
  arr = {1,3,4,2,2};
  cout << "The duplicate element is " << findDuplicate(arr) << endl;
}
Time Complexity:O(Nlogn + N)
Reason: NlogN for sorting the array and O(N) for traversing through the array and checking if adjacent elements are equal or not. But this will distort the array.

Space Complexity:O(1)
```


Solution 2:Using frequency array

```cpp
#include<bits/stdc++.h>

using namespace std;
int findDuplicate(vector < int > & arr)
{
  int n = arr.size();
  int freq[n + 1] = 
  {
    0
  };
  
  for (int i = 0; i < n; i++) 
  {
    if (freq[arr[i]] == 0) 
    {
      freq[arr[i]] += 1;
    }
    
    else 
    {
      return arr[i];
    }
  }
  return 0;
}

int main() 
{
  vector < int > arr;
  arr = {1,3,4,2,3};
  cout << "The duplicate element is " << findDuplicate(arr) << endl;
}


Time Complexity: O(N), as we are traversing through the array only once.
Space Complexity: O(N), as we are using extra space for frequency array.

```

Solution 3: Linked List cycle method

```cpp
#include<bits/stdc++.h>
using namespace std;

int findDuplicate(vector < int > & nums) 
{
  int slow = nums[0];
  int fast = nums[0];
  do 
  {
    slow = nums[slow];
    fast = nums[nums[fast]];
  } while (slow != fast);
  
  fast = nums[0];
  
  while (slow != fast) 
  {
    slow = nums[slow];
    fast = nums[fast];
  }
  return slow;
}
int main() 
{
  vector < int > arr;
  arr = {1,3,4,2,3};
  cout << "The duplicate element is " << findDuplicate(arr) << endl;
}

Time complexity: O(N). Since we traversed through the array only once.
Space complexity: O(1).

```
