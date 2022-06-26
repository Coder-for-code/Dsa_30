# [700. Search in a Binary Search Tree (Easy)](https://leetcode.com/problems/search-in-a-binary-search-tree/)

<p>You are given the <code>root</code> of a binary search tree (BST) and an integer <code>val</code>.</p>

<p>Find the node in the BST that the node's value equals <code>val</code> and return the subtree rooted with that node. If such a node does not exist, return <code>null</code>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2021/01/12/tree1.jpg" style="width: 422px; height: 302px;">
<pre><strong>Input:</strong> root = [4,2,7,1,3], val = 2
<strong>Output:</strong> [2,1,3]
</pre>

<p><strong>Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2021/01/12/tree2.jpg" style="width: 422px; height: 302px;">
<pre><strong>Input:</strong> root = [4,2,7,1,3], val = 5
<strong>Output:</strong> []
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is in the range <code>[1, 5000]</code>.</li>
	<li><code>1 &lt;= Node.val &lt;= 10<sup>7</sup></code></li>
	<li><code>root</code> is a binary search tree.</li>
	<li><code>1 &lt;= val &lt;= 10<sup>7</sup></code></li>
</ul>


**Companies**:  
[Microsoft](https://leetcode.com/company/microsoft), [Amazon](https://leetcode.com/company/amazon)

**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Binary Search Tree](https://leetcode.com/tag/binary-search-tree/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Closest Binary Search Tree Value (Easy)](https://leetcode.com/problems/closest-binary-search-tree-value/)
* [Insert into a Binary Search Tree (Medium)](https://leetcode.com/problems/insert-into-a-binary-search-tree/)

## Video Notes

![img431](https://user-images.githubusercontent.com/106215989/170554529-1ad608f8-1dd6-4954-aa2e-cda17ed5f1d1.jpg)
![img433](https://user-images.githubusercontent.com/106215989/170554535-d14b0de9-75c7-40f2-928f-f0b2616ae292.jpg)
![img435](https://user-images.githubusercontent.com/106215989/170554537-a6532639-2f1c-42a6-9687-518e5d8d2509.jpg)
![img437](https://user-images.githubusercontent.com/106215989/170554540-dc25e2c0-5f3c-4d34-b80c-cab933f0eb5c.jpg)
![img439](https://user-images.githubusercontent.com/106215989/170554542-293aad39-22d4-46c2-893d-82c5e2b411a5.jpg)
![img441](https://user-images.githubusercontent.com/106215989/170554548-839eb0d9-e80c-4ad8-af88-b1040fe3e696.jpg)


## Solution 1.

```cpp
// OJ: https://leetcode.com/problems/search-in-a-binary-search-tree/
// Time: O(H)
// Space: O(H)

class Solution 
{
public:
    TreeNode* searchBST(TreeNode* root, int val) 
    {
        if (!root) return nullptr;
        if (root->val == val) return root;
        return val > root->val ? searchBST(root->right, val) : searchBST(root->left, val);
    }
};
```
## Solution 2.

```cpp
// OJ: https://leetcode.com/problems/search-in-a-binary-search-tree/
// Time: O(H)
// Space: O(H)

class Solution
{
public:
    TreeNode* searchBST(TreeNode* root, int val) 
    {
        if(root==NULL)
            return NULL;
        if(root->val==val)
            return root;
        if(root->val<val)
            return searchBST(root->right,val);
        else
            return searchBST(root->left,val);
    }
};

```

## Solution 3.

```cpp
// OJ: https://leetcode.com/problems/search-in-a-binary-search-tree/
// Time: O(H)
// Space: O(H)

TreeNode* searchBST(TreeNode* root, int val) 
{
    while (root != nullptr && root->val != val) 
    {
      root = (root->val > val) ? root->left : root->right;
    }
    return root;
}
```
