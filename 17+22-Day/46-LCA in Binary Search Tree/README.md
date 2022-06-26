# [235. Lowest Common Ancestor of a Binary Search Tree (Easy)](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/)

<p>Given a binary search tree (BST), find the lowest common ancestor (LCA) of two given nodes in the BST.</p>

<p>According to the <a href="https://en.wikipedia.org/wiki/Lowest_common_ancestor" target="_blank">definition of LCA on Wikipedia</a>: “The lowest common ancestor is defined between two nodes <code>p</code> and <code>q</code> as the lowest node in <code>T</code> that has both <code>p</code> and <code>q</code> as descendants (where we allow <b>a node to be a descendant of itself</b>).”</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2018/12/14/binarysearchtree_improved.png" style="width: 200px; height: 190px;">
<pre><strong>Input:</strong> root = [6,2,8,0,4,7,9,null,null,3,5], p = 2, q = 8
<strong>Output:</strong> 6
<strong>Explanation:</strong> The LCA of nodes 2 and 8 is 6.
</pre>

<p><strong>Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2018/12/14/binarysearchtree_improved.png" style="width: 200px; height: 190px;">
<pre><strong>Input:</strong> root = [6,2,8,0,4,7,9,null,null,3,5], p = 2, q = 4
<strong>Output:</strong> 2
<strong>Explanation:</strong> The LCA of nodes 2 and 4 is 2, since a node can be a descendant of itself according to the LCA definition.
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> root = [2,1], p = 2, q = 1
<strong>Output:</strong> 2
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is in the range <code>[2, 10<sup>5</sup>]</code>.</li>
	<li><code>-10<sup>9</sup> &lt;= Node.val &lt;= 10<sup>9</sup></code></li>
	<li>All <code>Node.val</code> are <strong>unique</strong>.</li>
	<li><code>p != q</code></li>
	<li><code>p</code> and <code>q</code> will exist in the BST.</li>
</ul>


**Companies**:  
[LinkedIn](https://leetcode.com/company/linkedin), [Facebook](https://leetcode.com/company/facebook), [Microsoft](https://leetcode.com/company/microsoft), [Google](https://leetcode.com/company/google), [Uber](https://leetcode.com/company/uber)

**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Depth-First Search](https://leetcode.com/tag/depth-first-search/), [Binary Search Tree](https://leetcode.com/tag/binary-search-tree/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Lowest Common Ancestor of a Binary Tree (Medium)](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/)
* [Smallest Common Region (Medium)](https://leetcode.com/problems/smallest-common-region/)
* [Lowest Common Ancestor of a Binary Tree II (Medium)](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree-ii/)
* [Lowest Common Ancestor of a Binary Tree III (Medium)](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree-iii/)
* [Lowest Common Ancestor of a Binary Tree IV (Medium)](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree-iv/)

## Video Notes

![img535](https://user-images.githubusercontent.com/37560890/170562036-02692ffe-2df7-4dcf-b592-f6e564a63811.jpg)
![img537](https://user-images.githubusercontent.com/37560890/170562042-28a81dd1-1d15-460e-a8af-48fff65b67ed.jpg)
![img539](https://user-images.githubusercontent.com/37560890/170562047-e099def1-5dcc-4f33-895c-c00afffd0827.jpg)
![img541](https://user-images.githubusercontent.com/37560890/170562050-1502f630-d854-46de-8c6d-e9e586b9aca5.jpg)
![img543](https://user-images.githubusercontent.com/37560890/170562052-c427c491-71af-4734-9302-0c62c4f614e6.jpg)
![img545](https://user-images.githubusercontent.com/37560890/170562055-c6d99888-132f-4075-aafc-15fd59b87071.jpg)
![img547](https://user-images.githubusercontent.com/37560890/170562057-405158e4-263d-402c-ab1b-408bfda3a838.jpg)
![img549](https://user-images.githubusercontent.com/37560890/170562059-aed5f965-2a19-4bb1-8ea4-5bc4852334a4.jpg)
![img551](https://user-images.githubusercontent.com/37560890/170562064-9c9e90c7-36dd-4316-9108-06ddf1d061d6.jpg)
![img553](https://user-images.githubusercontent.com/37560890/170562066-71c44fa3-e458-48d1-a8de-fe8b7499068b.jpg)
![image](https://user-images.githubusercontent.com/37560890/175811926-000a1542-5b06-46fe-91a0-4e24244cd443.png)
![image](https://user-images.githubusercontent.com/37560890/175811943-a671d22a-4007-4292-8f8c-f6fd805751f8.png)


## Solution 1. DFS

```cpp
// OJ: https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/
// Time: O(H)
// Space: O(1)

class Solution 
{
public:
    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) 
    {
        if(root== NULL) return NULL;
        
        // Take the root val into the current
        int current= root->val;
        
        // Do both of them lie on the right so lets go on to the right
        if(current<p->val and current<q->val)
        {
            return lowestCommonAncestor(root->right,p,q);
        }
        
        // Do both of them lie on the left so lets go on to the left
        if(current>p->val and current>q->val)
        {
            return lowestCommonAncestor(root->left,p,q);
        }
        
        return root;
    }
};
```

