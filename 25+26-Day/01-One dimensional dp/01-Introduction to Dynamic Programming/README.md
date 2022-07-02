# [509. Fibonacci Number (Easy)](https://leetcode.com/problems/fibonacci-number/)

<p>The&nbsp;<b>Fibonacci numbers</b>, commonly denoted&nbsp;<code>F(n)</code>&nbsp;form a sequence, called the&nbsp;<b>Fibonacci sequence</b>, such that each number is the sum of the two preceding ones, starting from <code>0</code> and <code>1</code>. That is,</p>

<pre>F(0) = 0,&nbsp; &nbsp;F(1)&nbsp;= 1
F(N) = F(N - 1) + F(N - 2), for N &gt; 1.
</pre>

<p>Given <code>N</code>, calculate <code>F(N)</code>.</p>

<p>&nbsp;</p>

<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> 2
<strong>Output:</strong> 1
<strong>Explanation:</strong> F(2) = F(1) + F(0) = 1 + 0 = 1.
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> 3
<strong>Output:</strong> 2
<strong>Explanation:</strong> F(3) = F(2) + F(1) = 1 + 1 = 2.
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> 4
<strong>Output:</strong> 3
<strong>Explanation:</strong> F(4) = F(3) + F(2) = 2 + 1 = 3.
</pre>

<p>&nbsp;</p>

<p><strong>Note:</strong></p>

<p>0 ≤ <code>N</code> ≤ 30.</p>


**Related Topics**:  
[Array](https://leetcode.com/tag/array/)

**Similar Questions**:
* [Climbing Stairs (Easy)](https://leetcode.com/problems/climbing-stairs/)
* [Split Array into Fibonacci Sequence (Medium)](https://leetcode.com/problems/split-array-into-fibonacci-sequence/)
* [Length of Longest Fibonacci Subsequence (Medium)](https://leetcode.com/problems/length-of-longest-fibonacci-subsequence/)

## Video Notes

![vlcsnap-2022-07-01-08h48m32s873](https://user-images.githubusercontent.com/37560890/176990323-aeec7fd7-e136-4e9b-8194-bac5216bdb26.png)
![vlcsnap-2022-07-01-08h50m12s945](https://user-images.githubusercontent.com/37560890/176990324-332d21ec-4e0b-47d5-91da-d2cbcb6d77b9.png)
![vlcsnap-2022-07-02-11h33m08s985](https://user-images.githubusercontent.com/37560890/176990325-383f1f55-be56-478a-be24-b653eaa6e91e.png)
![vlcsnap-2022-07-02-11h33m34s166](https://user-images.githubusercontent.com/37560890/176990326-d0f0082c-996f-43c3-889b-ac0f5e52d45e.png)
![vlcsnap-2022-07-02-11h36m58s954](https://user-images.githubusercontent.com/37560890/176990328-80f6066f-bfd9-4ed1-9e1c-f19c0cfdd292.png)
![vlcsnap-2022-07-02-11h37m48s847](https://user-images.githubusercontent.com/37560890/176990329-f357ae57-71b7-4b03-b61d-d36f5462bc45.png)
![vlcsnap-2022-07-02-11h39m46s100](https://user-images.githubusercontent.com/37560890/176990330-1d116ed2-4b3e-4ad3-ae1a-2792beb12ce8.png)
![vlcsnap-2022-07-02-11h40m09s887](https://user-images.githubusercontent.com/37560890/176990331-ce29cccc-d519-4007-81b8-f2cfcfebde10.png)
![vlcsnap-2022-07-02-11h41m28s242](https://user-images.githubusercontent.com/37560890/176990332-2f10a166-b3fd-4760-9ca8-83414ddc6406.png)
![vlcsnap-2022-07-02-11h42m24s136](https://user-images.githubusercontent.com/37560890/176990334-e3d6682d-d7f5-45ab-aaa1-54ec97f65124.png)
![vlcsnap-2022-07-02-11h43m06s006](https://user-images.githubusercontent.com/37560890/176990335-0736e5ce-bdeb-4b76-8cfd-eb99625c8f60.png)
![vlcsnap-2022-07-02-11h44m46s312](https://user-images.githubusercontent.com/37560890/176990337-c0cb1585-775a-43de-98cf-e5ebad7c643b.png)
![vlcsnap-2022-07-02-11h45m10s388](https://user-images.githubusercontent.com/37560890/176990339-812e7b44-4e83-4728-9b90-2968ad264dbf.png)
![vlcsnap-2022-07-02-11h47m21s244](https://user-images.githubusercontent.com/37560890/176990342-8dc10269-2ec8-4b7f-a755-54867ef7715a.png)
![vlcsnap-2022-07-02-11h48m05s894](https://user-images.githubusercontent.com/37560890/176990344-9b70d815-930b-4dd7-ab79-3b6735be1162.png)
![vlcsnap-2022-07-02-11h56m15s468](https://user-images.githubusercontent.com/37560890/176990345-fd0b1a5b-2498-49a0-83f1-4d6eb0622f44.png)
![vlcsnap-2022-07-02-11h56m17s166](https://user-images.githubusercontent.com/37560890/176990347-4d419cd8-d696-47b4-8fa8-8dbd6d8e9b18.png)
![vlcsnap-2022-07-02-11h56m19s175](https://user-images.githubusercontent.com/37560890/176990348-ee925b99-f2c8-4e87-83d9-a5b4c0704c42.png)
![vlcsnap-2022-07-02-12h01m21s086](https://user-images.githubusercontent.com/37560890/176990349-03ba6996-26b6-458e-a3f7-d9a3c26de71d.png)
![vlcsnap-2022-07-02-12h04m29s140](https://user-images.githubusercontent.com/37560890/176990351-a48079c9-cadc-4a74-ba79-c5ad4bdeffa4.png)
![vlcsnap-2022-07-02-12h06m54s222](https://user-images.githubusercontent.com/37560890/176990352-17c24cdd-ed03-4212-826d-7746eac74829.png)
![vlcsnap-2022-07-02-12h07m40s792](https://user-images.githubusercontent.com/37560890/176990353-ab9426b3-3e6b-45a9-b5f8-5ccb7b6d2910.png)
![vlcsnap-2022-07-02-12h08m28s668](https://user-images.githubusercontent.com/37560890/176990354-e6cbecbe-0d79-4af1-ba44-ff829a1c4482.png)
![vlcsnap-2022-07-02-12h10m04s109](https://user-images.githubusercontent.com/37560890/176990355-7e424c9a-4f02-4ca8-b574-5c9d56ca93d7.png)
![vlcsnap-2022-07-02-12h12m49s032](https://user-images.githubusercontent.com/37560890/176990356-d5beb5a8-08a1-45a8-8c87-0bf9ea545eed.png)
![vlcsnap-2022-07-02-12h12m51s976](https://user-images.githubusercontent.com/37560890/176990357-bd268b15-5dc7-47db-964d-af549c6e1393.png)
![vlcsnap-2022-07-02-12h13m02s976](https://user-images.githubusercontent.com/37560890/176990358-52ecf126-71dc-4246-b828-1df93da877fc.png)
![vlcsnap-2022-07-02-12h13m21s135](https://user-images.githubusercontent.com/37560890/176990360-7f6eb658-8f42-442b-aae5-785df06cd0c9.png)
![vlcsnap-2022-07-02-12h14m16s729](https://user-images.githubusercontent.com/37560890/176990361-e122efb5-bba2-4d85-9455-441177a1183b.png)
![vlcsnap-2022-07-02-12h15m41s279](https://user-images.githubusercontent.com/37560890/176990363-fceb0783-9af2-4c8f-b076-720c50573e20.png)
![vlcsnap-2022-07-02-12h16m37s576](https://user-images.githubusercontent.com/37560890/176990365-4e6106b5-fe64-42a3-809d-ad509bfd10d8.png)
![vlcsnap-2022-07-02-12h16m56s729](https://user-images.githubusercontent.com/37560890/176990366-ef3b373b-1e96-47df-9a21-cd854f46f426.png)


## Solution 1.

```cpp
// OJ: https://leetcode.com/problems/fibonacci-number/
// Time: O(N)
// Space: O(1)

class Solution 
{
public:
    int fib(int N) 
    {
        if (N <= 1) return N;
        int prev = 0, cur = 1;
        while (--N > 0) 
	{
            int tmp = prev + cur;
            prev = cur;
            cur = tmp;
        }
        return cur;
    }
};
```
## Solution 1.

```cpp
// OJ: https://leetcode.com/problems/fibonacci-number/
// Time: O(N)
// Space: O(1)

class Solution 
{
public:
    int fib(int n) 
    {
        // If the n value is less then 1 return n
        if(n<=1) return n;
        
        // Initialize the prev and prev 2
        int prev2 = 0;
        int prev = 1;
        
        // Start from the 2n index and do the following operation
        for(int i=2;i<=n;i++)
        {
            int curr= prev + prev2;
            prev2= prev;
            prev= curr;
        }
        
        // Return prev because its n+1 so ans will be in prev
        return prev;
        
    }
};
```
