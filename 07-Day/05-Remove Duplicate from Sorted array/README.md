5. https://leetcode.com/problems/remove-duplicates-from-sorted-array/

```cpp
Solution 1: Brute Force

Intuition: 

We have to think of a data structure that does not store duplicate elements. 
So can we use a Hash set? Yes! We can. As we know HashSet only stores unique elements.

Approach: 

1. Declare a HashSet.
2. Run a for loop from starting to the end.
3. Put every element of the array in the set.
4. Store size of the set in a variable K.
5. Now put all elements of the set in the array from the starting of the array.
6. Return K.

#include<bits/stdc++.h>
using namespace std;

int removeDuplicates(int arr[])
{
  set < int > set;
  for (int i = 0; i < 7; i++) 
  {
    set.insert(arr[i]);
  }
  
  int k = set.size();
  int j = 0;
  
  for (int x: set) 
  {
    arr[j++] = x;
  }
  return k;
}

int main() 
{
  int arr[] = {1,1,2,2,2,3,3};
  int k = removeDuplicates(arr);
  cout << "The array after removing duplicate elements is " << endl;
  for (int i = 0; i < k; i++) 
  {
    cout << arr[i] << " ";
  }
}

Time complexity: O(n*log(n))+O(n)
Space Complexity: O(n) 

```

```cpp

Solution 2: Two pointers

Intuition:

We can think of using two pointers ‘i’ and ‘j’, we move ‘j’ till we don’t get a number
arr[j] which is different from arr[i].
As we got a unique number we will increase the i pointer and update its value by arr[j]. 

#include<bits/stdc++.h>
using namespace std;

int removeDuplicates(int arr[]) 
{
  int i = 0;
  for (int j = 1; j < 7; j++) 
  {
    if (arr[i] != arr[j])
    {
      i++;
      arr[i] = arr[j];
    }
  }
  return i + 1;
}

int main() 
{
  int arr[] = {1,1,2,2,2,3,3};
  int k = removeDuplicates(arr);
  cout << "The array after removing duplicate elements is " << endl;
  for (int i = 0; i < k; i++) 
  {
    cout << arr[i] << " ";
  }
}

Time complexity: O(n)
Space Complexity: O(1)

```
