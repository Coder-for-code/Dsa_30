# [131. Palindrome Partitioning (Medium)](https://leetcode.com/problems/palindrome-partitioning/)

<p>Given a string <code>s</code>, partition <code>s</code> such that every substring of the partition is a <strong>palindrome</strong>. Return all possible palindrome partitioning of <code>s</code>.</p>

<p>A <strong>palindrome</strong> string is a string that reads the same backward as forward.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<pre><strong>Input:</strong> s = "aab"
<strong>Output:</strong> [["a","a","b"],["aa","b"]]
</pre><p><strong>Example 2:</strong></p>
<pre><strong>Input:</strong> s = "a"
<strong>Output:</strong> [["a"]]
</pre>
<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= s.length &lt;= 16</code></li>
	<li><code>s</code> contains only lowercase English letters.</li>
</ul>


**Companies**:  
[Amazon](https://leetcode.com/company/amazon), [Google](https://leetcode.com/company/google), [tiktok](https://leetcode.com/company/tiktok), [ByteDance](https://leetcode.com/company/bytedance)

**Related Topics**:  
[String](https://leetcode.com/tag/string/), [Dynamic Programming](https://leetcode.com/tag/dynamic-programming/), [Backtracking](https://leetcode.com/tag/backtracking/)

**Similar Questions**:
* [Palindrome Partitioning II (Hard)](https://leetcode.com/problems/palindrome-partitioning-ii/)
* [Palindrome Partitioning IV (Hard)](https://leetcode.com/problems/palindrome-partitioning-iv/)

## Video Notes


![vlcsnap-2022-07-10-22h59m23s041](https://user-images.githubusercontent.com/37560890/178156115-8482e567-fc65-4fe6-95b7-29ce0c45d6ca.png)
![vlcsnap-2022-07-10-23h00m52s484](https://user-images.githubusercontent.com/37560890/178156117-d6bef48d-a3f4-4c1e-8041-ea0940d165a7.png)
![vlcsnap-2022-07-10-23h05m34s041](https://user-images.githubusercontent.com/37560890/178156119-cad2a4b5-358b-475f-96b7-43af84a4d422.png)
![vlcsnap-2022-07-10-23h10m10s553](https://user-images.githubusercontent.com/37560890/178156120-07cea794-7aaf-41fd-b287-d3ddd38b2096.png)
![vlcsnap-2022-07-10-23h10m52s226](https://user-images.githubusercontent.com/37560890/178156121-99d73db4-5085-475b-affe-603b8e9a52f4.png)
![vlcsnap-2022-07-10-23h12m22s874](https://user-images.githubusercontent.com/37560890/178156124-6c3ee9b0-1926-441f-8596-5bc7a90f482b.png)
![vlcsnap-2022-07-10-23h13m01s170](https://user-images.githubusercontent.com/37560890/178156126-a3751d8b-6744-4209-958b-06a4d85b5917.png)

## Solution 1. DFS

### Time complexity

In the worst case, `s` has all the same characters. If `s` is of length `N`, then there are `2^(N-1)` ways to partition it. For each partition, we also need to copy the strings over and testing if all its segments are palindromes, taking `O(N)` time. So overall the time complexity is `O(N * 2^N)`.

```cpp

// OJ: https://leetcode.com/problems/palindrome-partitioning/
// Time: O(N *  2^N)
// Space: O(N) extra space

class Solution
{
public:
    vector<vector<string>> partition(string s) 
    {
        vector<vector<string>> res; // which will be our answer
        vector<string> path; // as we are generating list everythime, so at the end this will be our list
        helper(0, s, path, res); // calling to recursion function start from index 0 and string s
        return res;
    }
    
    // Entire recursive function, that generates all the partition substring
    void helper(int index, string s, vector<string> &path, vector<vector<string>> &res)
    {
        // Base Condition, which means when we have done partition at the end (n), then add it to our ultimate result
        if(index == s.size())
	{
            res.push_back(path);
            return;
        }
        
	// Let's talk about partition
        for(int i = index; i < s.size(); i++)
	{
            if(isPalindrome(s, index, i))
	    { 
	    	// what we are checking over here is, if we partition the string from index to i Example-(0, 0) is palindrome or not
                path.push_back(s.substr(index, i - index + 1)); // take the substring and store it in our list & call the next substring from index + 1
                
		helper(i + 1, s, path, res); // as we have done for (0, 0) then our next will be from (1)
                path.pop_back(); // please make sure you remove when you backtrack. 
                
		// Why? Because let say i had partion y, so when i go back. I can't have yy
            }
        }
    }
    bool isPalindrome(string s, int start, int end)
    {
    	// A simple palindromic function start from 0 go till end. And basically keep on checking till they don't cross. 
        while(start <= end)
	{
            if(s[start++] != s[end--]) return false;
        }
        return true;
    }
};

```

