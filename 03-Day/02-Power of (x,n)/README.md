2. https://leetcode.com/problems/powx-n/

![4](https://user-images.githubusercontent.com/37560890/168951487-8353ea20-1d10-48f6-8586-c1d95c620a6b.jpg)

```cpp
Solution 1: Brute force approach 

Approach:  Looping from 1 to n and keeping a ans(double) variable. Now every time your loop runs, multiply x with ans. At last, we will return the ans.

Now if n is negative we must check if n is negative, if it is negative divide 1 by the and.

Code:

#include<bits/stdc++.h>
using namespace std;
double myPow(double x, int n)
{
      double ans = 1.0;
      for (int i = 0; i < n; i++) 
      {
        ans = ans * x;
      }
      return ans;
}
int main()
{
    cout<<myPow(2,10)<<endl;
}

Time Complexity: O(N)
Space Complexity: O(1)
```

```cpp
Solution 2: Using Binary Exponentiation

#include<bits/stdc++.h>

using namespace std;
double myPow(double x, int n) {
  double ans = 1.0;
  long long nn = n;
  if (nn < 0) nn = -1 * nn;
  while (nn) {
    if (nn % 2) {
      ans = ans * x;
      nn = nn - 1;
    } else {
      x = x * x;
      nn = nn / 2;
    }
  }
  if (n < 0) ans = (double)(1.0) / (double)(ans);
  return ans;
}

int main() {
  cout << myPow(2, 10) << endl;
}

Time Complexity: O(log n)
Space Complexity: O(1)
```
