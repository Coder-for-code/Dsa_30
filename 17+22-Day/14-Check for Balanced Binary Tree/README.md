# [110. Balanced Binary Tree (Easy)](https://leetcode.com/problems/balanced-binary-tree/)

<p>Given a binary tree, determine if it is height-balanced.</p>

<p>For this problem, a height-balanced binary tree is defined as:</p>

<blockquote>
<p>a binary tree in which the left and right subtrees of <em>every</em> node differ in height by no more than 1.</p>
</blockquote>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/10/06/balance_1.jpg" style="width: 342px; height: 221px;">
<pre><strong>Input:</strong> root = [3,9,20,null,null,15,7]
<strong>Output:</strong> true
</pre>

<p><strong>Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/10/06/balance_2.jpg" style="width: 452px; height: 301px;">
<pre><strong>Input:</strong> root = [1,2,2,3,3,null,null,4,4]
<strong>Output:</strong> false
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> root = []
<strong>Output:</strong> true
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is in the range <code>[0, 5000]</code>.</li>
	<li><code>-10<sup>4</sup> &lt;= Node.val &lt;= 10<sup>4</sup></code></li>
</ul>


**Companies**:  
[Amazon](https://leetcode.com/company/amazon), [Google](https://leetcode.com/company/google), [Facebook](https://leetcode.com/company/facebook), [Spotify](https://leetcode.com/company/spotify)

**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Depth-First Search](https://leetcode.com/tag/depth-first-search/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Maximum Depth of Binary Tree (Easy)](https://leetcode.com/problems/maximum-depth-of-binary-tree/)

## Video Notes

![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0117](https://user-images.githubusercontent.com/106215989/170275897-3c894315-fc15-4865-b328-2197cbeb8641.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0118](https://user-images.githubusercontent.com/106215989/170275905-792238c9-822d-4e8d-9922-f5a15618e0b6.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0119](https://user-images.githubusercontent.com/106215989/170275913-5476a82a-93ef-497b-b378-90bff21db383.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0120](https://user-images.githubusercontent.com/106215989/170275917-b9286ad0-b8c1-4f6f-8b60-7d36d42b9843.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0121](https://user-images.githubusercontent.com/106215989/170275922-cc584043-1c52-48e6-8240-aa9df7066ecc.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0122](https://user-images.githubusercontent.com/106215989/170275926-446c9c25-b150-403b-8fae-90e9ee839690.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0123](https://user-images.githubusercontent.com/106215989/170275929-05e98cbc-376e-4cbc-8a35-293dd2d5d933.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0124](https://user-images.githubusercontent.com/106215989/170275933-aa7a1911-dd0a-4b2c-9dcb-509af8d35e0e.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0125](https://user-images.githubusercontent.com/106215989/170275935-0616d84d-4ea9-4524-a652-dee9e0327e5d.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0126](https://user-images.githubusercontent.com/106215989/170275937-f00f1260-16d6-4002-ac91-fb964451f5a1.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0127](https://user-images.githubusercontent.com/106215989/170275939-869046f9-4eb8-4d69-870f-9fa090153565.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0128](https://user-images.githubusercontent.com/106215989/170275944-31d2f5f7-2374-430f-844a-d65c656bf5ae.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0129](https://user-images.githubusercontent.com/106215989/170275949-4d34f30c-0dec-41cc-a924-382e5887f95c.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0130](https://user-images.githubusercontent.com/106215989/170275954-077887e4-72fe-431a-a182-3479cf906856.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0131](https://user-images.githubusercontent.com/106215989/170275957-11db777f-681a-4a7a-9a2a-04f31846fc0f.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0132](https://user-images.githubusercontent.com/106215989/170275960-c99f1631-3618-4ecc-9d92-542bc4f855dc.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0133](https://user-images.githubusercontent.com/106215989/170275964-db85230c-133c-41a7-8235-94f92db064c2.jpg)


## Solution 1. Dfs


```cpp
// OJ: https://leetcode.com/problems/balanced-binary-tree/
// Time: O(N)
// Space: O(H)

class Solution 
{
public:
    
    
    bool isBalanced(TreeNode* root) 
    {
        return dfs_Height(root) !=-1;
    }
    
    // Helper Method
    int dfs_Height(TreeNode *root)
    {
        // Base case checking
        if(!root) return 0;
        
        // Compute the left height
        int left_height= dfs_Height(root->left);
        if(left_height==-1) return -1;
        
        // Compute the right height
        int right_height= dfs_Height(root->right);
        if(right_height==-1) return -1;
        
        // Check the condition as per the question
        if(abs(left_height-right_height)>1) return -1;
        
        // Return max height
        return max(left_height,right_height)+1;
        
    }
};
```

## Solution 2. Dfs

```cpp
// OJ: https://leetcode.com/problems/balanced-binary-tree/
// Time: O(N)
// Space: O(H)

class Solution 
{
private:
    bool isBalanced(TreeNode* root, int &h) 
    {
        h = 0;
        if (!root) return true;
        int L = 0, R = 0;
        bool b = isBalanced(root->left, L) && isBalanced(root->right, R) && abs(L - R) <= 1;
        h = 1 + max(L, R);
        return b;
    }
public:
    bool isBalanced(TreeNode* root) 
    {
        int h;
        return isBalanced(root, h);
    }
};
```

