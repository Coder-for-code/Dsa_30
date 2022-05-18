4. https://leetcode.com/problems/reverse-pairs/

![8](https://user-images.githubusercontent.com/37560890/168953836-519876b8-b2e0-489b-a289-5bb8b281b9f5.jpg)

```cpp
Solution 1: Brute Force Approach

Intuition : 

As we can see from the given question that i < j, So we can 
just use 2 nested loops and check for the given condition which is arr [i] > 2* arr[j].

Approach:

We will be having 2 nested For loops the outer loop having i as pointer 
The inner loop with j as pointer and we will make sure that 
0 <= i < j < arr.length() and also arr[i] > 2*arr[j] condition must be satisfied.
Code:

#include<bits/stdc++.h>
using namespace std;

int reversePairs(vector < int > & arr) 
{
      int Pairs = 0;
      for (int i = 0; i < arr.size(); i++) 
      {
        for (int j = i + 1; j < arr.size(); j++) 
	{
          if (arr[i] > 2 * arr[j]) Pairs++;
        }
      }
      return Pairs;
    }


int main()
{
    vector<int> arr{1,3,2,3,1};
    cout<<"The Total Reverse Pairs are "<<reversePairs(arr);
}

Time Complexity: O (N^2) ( Nested Loops )
Space Complexity:  O(1)


```


```cpp
Solution 2: Optimal Solution

Intuition:

-> We will be using the Merge Sort Algorithm to solve this problem. 
We split the whole array into 2  parts creating a Merge Sort Tree-like structure. 
During the conquer step we do the following task : 

-> We take the left half of the Array and Right half of the Array, both are sorted in themselves. 

-> We will be checking the following condition arr[i] <= 2*arr[j] 
where i is the pointer in the Left Array and j is the pointer in the Right Array. 

-> If at any point arr[i] <= 2*arr[j] , we add 1  to the answer as this pair has a contribution to the answer. 

-> If Left Array gets exhausted before Right Array we keep on adding 
the distance j pointer traveled as both the arrays are Sorted so 
the next ith element from Left Subarray will equally contribute to the answer.

-> The moment when both Arrays get exhausted we perform a merge operation.
This goes on until we get the original array as a Sorted array.

#include<bits/stdc++.h>
using namespace std;

int Merge(vector < int > & nums, int low, int mid, int high) 
{
  int total = 0;
  int j = mid + 1;
  for (int i = low; i <= mid; i++) 
  {
    while (j <= high && nums[i] > 2 LL * nums[j]) 
    {
      j++;
    }
    total += (j - (mid + 1));
  }

  vector < int > t;
  int left = low, right = mid + 1;

  while (left <= mid && right <= high) 
  {

    if (nums[left] <= nums[right]) 
    {
      t.push_back(nums[left++]);
    } 
    
    else 
    {
      t.push_back(nums[right++]);
    }
  }

  while (left <= mid) 
  {
    t.push_back(nums[left++]);
  }
  
  while (right <= high) 
  {
    t.push_back(nums[right++]);
  }

  for (int i = low; i <= high; i++) 
  {
    nums[i] = t[i - low];
  }
  
  return total;
}
int MergeSort(vector < int > & nums, int low, int high) 
{

  if (low >= high) return 0;
  int mid = (low + high) / 2;
  int inv = MergeSort(nums, low, mid);
  inv += MergeSort(nums, mid + 1, high);
  inv += Merge(nums, low, mid, high);
  return inv;
}

int reversePairs(vector < int > & arr) 
{
  return MergeSort(arr, 0, arr.size() - 1);
}

int main() 
{
  vector<int> arr{1,3,2,3,1};
  cout << "The Total Reverse Pairs are " << reversePairs(arr);
}

Time Complexity : O( N log N ) + O (N) + O (N)   
Reason : O(N) – Merge operation , 
O(N) – counting operation ( at each iteration of i , j doesn’t start from 0 . Both of them move linearly ) 

Space Complexity : O(N)  Reason : O(N) – Temporary vector



```
