# [70. Climbing Stairs (Easy)](https://leetcode.com/problems/climbing-stairs/)

<p>You are climbing a staircase. It takes <code>n</code> steps to reach the top.</p>

<p>Each time you can either climb <code>1</code> or <code>2</code> steps. In how many distinct ways can you climb to the top?</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> n = 2
<strong>Output:</strong> 2
<strong>Explanation:</strong> There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> n = 3
<strong>Output:</strong> 3
<strong>Explanation:</strong> There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= n &lt;= 45</code></li>
</ul>


**Companies**:  
[Amazon](https://leetcode.com/company/amazon), [Google](https://leetcode.com/company/google), [Microsoft](https://leetcode.com/company/microsoft), [Bloomberg](https://leetcode.com/company/bloomberg), [Expedia](https://leetcode.com/company/expedia), [Adobe](https://leetcode.com/company/adobe), [Uber](https://leetcode.com/company/uber), [Apple](https://leetcode.com/company/apple), [LinkedIn](https://leetcode.com/company/linkedin), [Facebook](https://leetcode.com/company/facebook), [Walmart Labs](https://leetcode.com/company/walmart-labs), [Morgan Stanley](https://leetcode.com/company/morgan-stanley), [Twilio](https://leetcode.com/company/twilio)

**Related Topics**:  
[Math](https://leetcode.com/tag/math/), [Dynamic Programming](https://leetcode.com/tag/dynamic-programming/), [Memoization](https://leetcode.com/tag/memoization/)

**Similar Questions**:
* [Min Cost Climbing Stairs (Easy)](https://leetcode.com/problems/min-cost-climbing-stairs/)
* [Fibonacci Number (Easy)](https://leetcode.com/problems/fibonacci-number/)
* [N-th Tribonacci Number (Easy)](https://leetcode.com/problems/n-th-tribonacci-number/)

## Video Notes

![vlcsnap-2022-07-02-13h32m03s180](https://user-images.githubusercontent.com/37560890/176992912-7da72647-bb32-41cf-9975-27511883b445.png)
![vlcsnap-2022-07-02-13h35m26s834](https://user-images.githubusercontent.com/37560890/176992914-4875a4f4-25ac-4073-80d1-1dd6b2f5baf6.png)
![vlcsnap-2022-07-02-13h35m47s903](https://user-images.githubusercontent.com/37560890/176992915-002ecf7d-3e5f-486d-b37f-6117f86467a9.png)
![vlcsnap-2022-07-02-13h36m07s767](https://user-images.githubusercontent.com/37560890/176992916-ffa022a6-1e06-4e24-a2e2-07fb1826f43b.png)
![vlcsnap-2022-07-02-13h37m12s478](https://user-images.githubusercontent.com/37560890/176992917-faaad136-d805-4b1f-b182-82a76e9153fc.png)
![vlcsnap-2022-07-02-13h38m01s889](https://user-images.githubusercontent.com/37560890/176992919-7f2c0780-38cc-41be-b697-fcf27932dff5.png)
![vlcsnap-2022-07-02-13h40m06s222](https://user-images.githubusercontent.com/37560890/176992920-5194ee69-f4e1-4de2-b682-fc342a42a242.png)
![vlcsnap-2022-07-02-13h40m54s244](https://user-images.githubusercontent.com/37560890/176992922-744ff567-8f40-43fc-8b82-c94426e77e62.png)
![vlcsnap-2022-07-02-13h41m59s711](https://user-images.githubusercontent.com/37560890/176992923-1fc882ba-ff78-4617-b035-4808abb7e831.png)
![vlcsnap-2022-07-02-13h42m14s285](https://user-images.githubusercontent.com/37560890/176992924-3020a34d-7ee0-4c33-810f-3c75cbf23f8f.png)
![vlcsnap-2022-07-02-13h42m38s267](https://user-images.githubusercontent.com/37560890/176992926-997e42b5-fff3-4c86-a164-ca563ea1b114.png)
![vlcsnap-2022-07-02-13h42m53s057](https://user-images.githubusercontent.com/37560890/176992927-ddfcf7db-4b3b-4383-aadc-3e06b2fa7006.png)
![vlcsnap-2022-07-02-13h43m00s262](https://user-images.githubusercontent.com/37560890/176992928-1642208a-db3f-4c76-a230-da19f5895a9b.png)
![vlcsnap-2022-07-02-13h43m02s810](https://user-images.githubusercontent.com/37560890/176992929-842d9746-5131-4fc8-81fe-3bdb61d2c464.png)
![vlcsnap-2022-07-02-13h43m29s545](https://user-images.githubusercontent.com/37560890/176992930-01c70e00-d074-43ef-b9e8-000e92fa7fde.png)
![vlcsnap-2022-07-02-13h43m35s683](https://user-images.githubusercontent.com/37560890/176992931-13de1dbb-ea5f-428f-999e-b2320e47395e.png)
![vlcsnap-2022-07-02-13h43m53s564](https://user-images.githubusercontent.com/37560890/176992932-cdd101ed-c469-4880-90da-2760fae7629d.png)
![image](https://user-images.githubusercontent.com/37560890/176993083-b310e9d2-4a78-4c7b-b14e-23205b9e4c2b.png)

## Solution 1. DP

```cpp
// OJ: https://leetcode.com/problems/climbing-stairs/
// Time: O(N)
// Space: O(1)

class Solution
{
public:
    int climbStairs(int n) 
    {
        // If the n value is less then 1 return n
        if(n<=0) return 0;
        if(n==1) return 1;
        if(n==2) return 2;
        // Initialize the prev and prev 2
        int prev2 =1;
        int prev = 2;
        
        // Start from the 2n index and do the following operation
        for(int i=2;i<n;i++)
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

or

```cpp

class Solution 
{ 
public:
    int climbStairs(int n) 
    {
        if (n <= 1) return n;
        int dp[3];
        dp[1] = 1;
        dp[2] = 2;
        for (int i = 3; i <= n; i++) 
	{
            int sum = dp[1] + dp[2];
            dp[1] = dp[2];
            dp[2] = sum;
	}
        return dp[2];
    }
};

```

## Solution 2. DP

```cpp
// OJ: https://leetcode.com/problems/climbing-stairs/
// Time: O(N)
// Space: O(1)

class Solution 
{
public:
    int climbStairs(int n) 
    {
        int ans = 1, prev = 1;
        while (--n) 
	{
            ans += prev;
            prev = ans - prev;
        }
        return ans;
    }
};
```

Or

```cpp
// OJ: https://leetcode.com/problems/climbing-stairs/
// Time: O(N)
// Space: O(1)

class Solution 
{
public:
    int climbStairs(int n) 
    {
        int prev = 0, cur = 1;
        while (n--) 
	{
            int next = cur + prev;
            prev = cur;
            cur = next;
        }
        return cur;
    }
};
```
