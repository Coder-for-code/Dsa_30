# [104. Maximum Depth of Binary Tree (Easy)](https://leetcode.com/problems/maximum-depth-of-binary-tree/)

<p>Given the <code>root</code> of a binary tree, return <em>its maximum depth</em>.</p>

<p>A binary tree's <strong>maximum depth</strong>&nbsp;is the number of nodes along the longest path from the root node down to the farthest leaf node.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/11/26/tmp-tree.jpg" style="width: 400px; height: 277px;">
<pre><strong>Input:</strong> root = [3,9,20,null,null,15,7]
<strong>Output:</strong> 3
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> root = [1,null,2]
<strong>Output:</strong> 2
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is in the range <code>[0, 10<sup>4</sup>]</code>.</li>
	<li><code>-100 &lt;= Node.val &lt;= 100</code></li>
</ul>


**Companies**:  
[LinkedIn](https://leetcode.com/company/linkedin), [Amazon](https://leetcode.com/company/amazon), [Google](https://leetcode.com/company/google), [Spotify](https://leetcode.com/company/spotify), [Microsoft](https://leetcode.com/company/microsoft)

**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Depth-First Search](https://leetcode.com/tag/depth-first-search/), [Breadth-First Search](https://leetcode.com/tag/breadth-first-search/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Balanced Binary Tree (Easy)](https://leetcode.com/problems/balanced-binary-tree/)
* [Minimum Depth of Binary Tree (Easy)](https://leetcode.com/problems/minimum-depth-of-binary-tree/)
* [Maximum Depth of N-ary Tree (Easy)](https://leetcode.com/problems/maximum-depth-of-n-ary-tree/)
* [Time Needed to Inform All Employees (Medium)](https://leetcode.com/problems/time-needed-to-inform-all-employees/)

## Video Notes

![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0110](https://user-images.githubusercontent.com/37560890/170274974-5915ed4d-9558-4104-b493-02948c37ae56.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0111](https://user-images.githubusercontent.com/37560890/170274995-11cd0bef-4752-4303-b9bf-e909bed9b954.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0112](https://user-images.githubusercontent.com/37560890/170275008-a91bbd83-8c96-4a23-bdd6-9f1e35214e39.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0113](https://user-images.githubusercontent.com/37560890/170275019-c453874f-672c-4543-9f74-5e1ac3f8cef5.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0114](https://user-images.githubusercontent.com/37560890/170275028-5128c98d-5814-4918-98e9-c6e9c06facf4.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0115](https://user-images.githubusercontent.com/37560890/170275041-e600f590-07ae-4390-8da7-ec92b0ca679f.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0116](https://user-images.githubusercontent.com/37560890/170275062-6a0f16ac-7f40-4cb2-9a42-bf55d1887d6d.jpg)

![dfs](https://user-images.githubusercontent.com/106215989/173235556-d6dbbf79-d4c0-4ba2-b397-ecd389b5c74e.png)



## Solution 1. Dfs

```cpp
// OJ: https://leetcode.com/problems/maximum-depth-of-binary-tree/
// Time: O(N)
// Space: O(N)

class Solution
{
public:
    int maxDepth(TreeNode* root) 
    {
        return root ? 1 + max(maxDepth(root->left), maxDepth(root->right)) : 0;
    }
};
```


## Solution 2. Dfs

```cpp
class Solution 
{
public:
    int maxDepth(TreeNode* root) 
    {
        // If the root is not pointing to someone return 0
        if(!root) return 0;
        
        // Compute the left and right height
        int left_height= maxDepth(root->left);
        int right_height= maxDepth(root->right);
        
        // Finally return the 1+max lh,rh
        return 1+ max(left_height, right_height);
    }
};
```

## Solution 3. Bfs

```cpp
Time Complexity: O (n)
Space Complexity: O (n)

class Solution 
{
public:

    int maxDepth(TreeNode* root) 
    {
        if (root==NULL) return 0; 
        queue<TreeNode*> q;
        q.push(root);
        int depth=0;
        
        while (!q.empty()) 
        {
            ++depth;
            int s=q.size();
        
            for (int i=0; i<s; i++) 
            {
                TreeNode* front=q.front();
                q.pop();
                
                if (front->left) q.push(front->left);
                if (front->right) q.push(front->right);
            }
        }
    return depth;
    }
};

```
