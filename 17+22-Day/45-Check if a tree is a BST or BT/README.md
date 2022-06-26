# [98. Validate Binary Search Tree (Medium)](https://leetcode.com/problems/validate-binary-search-tree/)

<p>Given the <code>root</code> of a binary tree, <em>determine if it is a valid binary search tree (BST)</em>.</p>

<p>A <strong>valid BST</strong> is defined as follows:</p>

<ul>
	<li>The left subtree of a node contains only nodes with keys <strong>less than</strong> the node's key.</li>
	<li>The right subtree of a node contains only nodes with keys <strong>greater than</strong> the node's key.</li>
	<li>Both the left and right subtrees must also be binary search trees.</li>
</ul>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/12/01/tree1.jpg" style="width: 302px; height: 182px;">
<pre><strong>Input:</strong> root = [2,1,3]
<strong>Output:</strong> true
</pre>

<p><strong>Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/12/01/tree2.jpg" style="width: 422px; height: 292px;">
<pre><strong>Input:</strong> root = [5,1,4,null,null,3,6]
<strong>Output:</strong> false
<strong>Explanation:</strong> The root node's value is 5 but its right child's value is 4.
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is in the range <code>[1, 10<sup>4</sup>]</code>.</li>
	<li><code>-2<sup>31</sup> &lt;= Node.val &lt;= 2<sup>31</sup> - 1</code></li>
</ul>


**Companies**:  
[Amazon](https://leetcode.com/company/amazon), [Facebook](https://leetcode.com/company/facebook), [Bloomberg](https://leetcode.com/company/bloomberg), [Microsoft](https://leetcode.com/company/microsoft), [Zillow](https://leetcode.com/company/zillow), [Apple](https://leetcode.com/company/apple), [Google](https://leetcode.com/company/google), [Uber](https://leetcode.com/company/uber), [ByteDance](https://leetcode.com/company/bytedance)

**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Depth-First Search](https://leetcode.com/tag/depth-first-search/), [Binary Search Tree](https://leetcode.com/tag/binary-search-tree/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Binary Tree Inorder Traversal (Easy)](https://leetcode.com/problems/binary-tree-inorder-traversal/)
* [Find Mode in Binary Search Tree (Easy)](https://leetcode.com/problems/find-mode-in-binary-search-tree/)

## Video Notes

![img599](https://user-images.githubusercontent.com/106215989/170564705-27264e4d-39a2-4cd9-baeb-dca9618fe852.jpg)
![img601](https://user-images.githubusercontent.com/106215989/170564711-f1bf330a-2f9a-4514-b9e3-029d8b7b3a9d.jpg)
![img603](https://user-images.githubusercontent.com/106215989/170564715-9145990a-6f36-4042-9fdb-4163b1472ed3.jpg)
![img605](https://user-images.githubusercontent.com/106215989/170564718-cfd24042-8b35-4799-9395-66882cba8881.jpg)
![img607](https://user-images.githubusercontent.com/106215989/170564720-a15ba4f3-cb7d-4bd1-8a54-f7fbf336ed70.jpg)
![img609](https://user-images.githubusercontent.com/106215989/170564724-c79b37ef-31ff-4d7d-9f9a-1a3393c2922f.jpg)
![img611](https://user-images.githubusercontent.com/106215989/170564726-a1c15754-6247-429b-864a-28d1aee8f47a.jpg)
![img613](https://user-images.githubusercontent.com/106215989/170564728-c2ec5cbd-467a-4e1b-9c29-826bb914e765.jpg)
![img615](https://user-images.githubusercontent.com/106215989/170564730-56d178fe-56d2-4b45-b551-4a18bbdc58a5.jpg)
![img617](https://user-images.githubusercontent.com/106215989/170564731-0a355747-e317-499e-a5c5-2cdecef6370a.jpg)
![img619](https://user-images.githubusercontent.com/106215989/170564735-c30cc308-d62b-4fe4-ae49-a0f09c227816.jpg)
![img621](https://user-images.githubusercontent.com/106215989/170564738-853c4531-c970-4d08-8be1-29b4feaccd43.jpg)
![img623](https://user-images.githubusercontent.com/106215989/170564741-a17f4a71-43cf-44f6-8863-047c93734dd4.jpg)
![img625](https://user-images.githubusercontent.com/106215989/170564746-dd866ebc-5e2b-4205-8c1c-db9173603159.jpg)
![img627](https://user-images.githubusercontent.com/106215989/170564749-621a6d7b-2b46-4961-b8e3-81cfa482132b.jpg)
![img629](https://user-images.githubusercontent.com/106215989/170564750-a6fe436f-5b14-481f-ab86-12d5be0d29a3.jpg)
![img631](https://user-images.githubusercontent.com/106215989/170564756-dc50caef-c36d-4825-9544-5ad3f0eac320.jpg)
![img633](https://user-images.githubusercontent.com/106215989/170564760-a6a66137-6bb6-4eb5-a338-ddcd956196ce.jpg)


## Solution 0.

```cpp
// OJ: https://leetcode.com/problems/validate-binary-search-tree
// Time: O(N)
// Space: O(H)

class Solution
{
public:
    bool isValidBST(TreeNode* root) 
    {
        return fun(root, NULL, NULL);
    }
    
    bool fun(TreeNode* root, TreeNode* max, TreeNode* min)
    {
        if(root==NULL)
        {
            return true;
        }
		// Using the same above logic
		//Just check if max or min-node is NULL, then follow it as true
        if((min==NULL || root->val > min->val) && (max==NULL || root->val < max->val))
        {
            return fun(root->left, root, min) && fun(root->right, max, root);
        }
        return false;
    }
};
```
## Solution 1. Pre-order Traversal

```cpp
// OJ: https://leetcode.com/problems/validate-binary-search-tree
// Time: O(N)
// Space: O(H)

class Solution 
{
public:
    bool isValidBST(TreeNode* root, TreeNode *left = NULL, TreeNode *right = NULL) 
    {
        if (!root) return true;
        if ((left && root->val <= left->val) || (right && root->val >= right->val)) return false;
        return isValidBST(root->left, left, root) && isValidBST(root->right, root, right);
    }
};
```

Or

```cpp
// OJ: https://leetcode.com/problems/validate-binary-search-tree/
// Time: O(N)
// Space: O(H)

class Solution 
{
public:
    bool isValidBST(TreeNode* root, long left = LONG_MIN, long right = LONG_MAX) 
    {
        if (!root) return true;
        if (root->val <= left || root->val >= right) return false;
        return isValidBST(root->left, left, root->val) && isValidBST(root->right, root->val, right);
    }
};
```

## Solution 2. In-order traversal

```cpp
// OJ: https://leetcode.com/problems/validate-binary-search-tree
// Time: O(N)
// Space: O(logN)

class Solution 
{
    TreeNode *prev = NULL;
public:
    bool isValidBST(TreeNode* root) 
    {
        if (!root) return true;
        if (!isValidBST(root->left) || (prev && prev->val >= root->val)) return false; 
        prev = root;
        return isValidBST(root->right);
    }
};
```

