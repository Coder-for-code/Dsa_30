5. https://www.interviewbit.com/problems/subarray-with-given-xor/

![8](https://user-images.githubusercontent.com/37560890/168963455-dbe7e203-2ea1-4ab5-8fee-287cf4fffe08.jpg)
![9](https://user-images.githubusercontent.com/37560890/168963462-deb69778-2fbb-4d3d-a343-28c270dcd0a2.jpg)

```cpp
Solution 1: Brute Force

Intuition: 

The brute force solution is to generate all possible subarrays.
For each generated subarray we get the respective XOR and then check if this XOR is equal to B. 
If it is then we increment the count. In the end, we will get the count of all possible subarrays that have XOR equal to B.

Approach:

1. Generate subarrays: To generate all possible subarrays, we use the same old technique of nested loops. 
2. For each value of the outer loop (i loop), the inner loop(j loop) runs from i till the last element. 
Each iteration of the inner loop gives a new subarray. 

3. Maintain XOR: Since each iteration of the inner loop gives a new subarray, 
we maintain a variable X, in which we keep the XOR of the current subarray. 

4. Check and Count: Before moving to the next iteration of the inner loop (that is before going to the next subarray), 
we check if the current XOR is equal to B, if it is then we increment the counter (counter also has to be maintained).

Code:

#include<bits/stdc++.h>
using namespace std;

class Solution
{
    public:
    int solve(vector<int> &A, int B) 
    {
    long long c=0;
    
    for(int i=0;i<A.size();i++)
    {
        int current_xor = 0;
        
	for(int j=i;j<A.size();j++)
	{
            current_xor^=A[j];
            if(current_xor==B) c++;
        }
    }
    return c;
}
};

int main()
{   vector<int> A{ 4,2,2,6,4 };
    Solution obj;
    int totalCount= obj.solve(A,6);
    cout<<"The total number of subarrays having a given XOR k is "<<totalCount<<endl;
}

Time Complexity: O(N2)
Space Complexity: O(1)
```

```cpp
Solution 2: Prefix xor and map

Intuition:

The main idea is to observe the prefix xor of the array. 
Prefix Xor is just another array, where each index contains XOR of all elements of the original array 
starting from index 0 up to that index. In other words
prefix_xor[i] = XOR(a[0], a[1], a[2],……,a[I])

Once we have made the prefix xor array, we observe a fact:

P = xor(a[0], a[1], a[2],……, a[q], a[q+1],….., a[p])
Q = xor(a[0], a[1], a[2],……, a[q])

Therefore,

P^Q = xor(a[q+1],….., a[p]) = M                                
So, now we understand that from the prefix xor array when we XOR two elements at different indices
we get the xor of the elements (in the original array) that were between those indices.

Let’s say we did XOR(P, B) and we got Q (B is the integer given in question). What does this mean?
This means that the subarray between q and p is having xor = B. To understand this we just use simple equations:

P^B = Q
=> P^B^P = Q^P
=> B = Q^P  

And we already know by fact 1 that Q^P will give xor of all elements between q and p.
Therefore, the subarray between q and p has xor = B.

Suppose we did XOR(P, B) and we got Q (B is the integer given in question).
But there is more than one Q before p.

In this case, there are two subarrays that have XOR = B. Subarrays between q1 to p and q2 to p. 

IMP NOTE: although we talk about prefix xor “array”, it should be noted that at a time we need only one element of this array. Hence, we can just use a variable to maintain the prefix xor. 

Approach:

1. We need to traverse the array while we maintain variables for current_perfix_xor, counter, 
and also a map to keep track of visited xors. 

2. This map will maintain the frequency count of all previous visited current_prefix_xor values. 

3. If for any index current_prefix_xor is equal to B, we increment the counter. 

4. If for any index we find that Z is present in the visited map, we increment the counter by visited[Z]
(Z=current_prefi_xor^B).

5. At every index, we insert the current_prefix_xor into the visited map with its frequency.

Code:

#include<bits/stdc++.h>
using namespace std;
class Solution
{
    public:
    int solve(vector<int> &A, int B)
    {
    unordered_map<int,int>visited;
    int cpx = 0;
    long long c=0;
    
    for(int i=0;i<A.size();i++)
    {
        cpx^=A[i];
        if(cpx==B) c++;
        int h = cpx^B;
        
	if(visited.find(h)!=visited.end())
	{
            c=c+visited[h];
        }
        visited[cpx]++;
    }
    return c;
}
};


int main()
{   vector<int> A{ 4,2,2,6,4 };
    Solution obj;
    int totalCount= obj.solve(A,6);
    cout<<"The total number of subarrays having a given XOR k is "<<totalCount<<endl;
}

Time Complexity: O(N)
Space Complexity: O(N)

NOTE: 

The complexity of worst-case searching for an unordered_map can go up to O(N),
hence it is safer to use ordered_map. But if we use ordered_map then the time complexity will be O(N logN).
Space complexity will be the same in both cases.
```
