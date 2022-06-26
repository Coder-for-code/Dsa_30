# [1008. Construct Binary Search Tree from Preorder Traversal (Medium)](https://leetcode.com/problems/construct-binary-search-tree-from-preorder-traversal/)

<p>Return the root node of a binary <strong>search</strong> tree that matches the given <code>preorder</code> traversal.</p>

<p><em>(Recall that a binary search tree&nbsp;is a binary tree where for every <font face="monospace">node</font>, any descendant of <code>node.left</code> has a value <code>&lt;</code>&nbsp;<code>node.val</code>, and any descendant of <code>node.right</code> has a value <code>&gt;</code>&nbsp;<code>node.val</code>.&nbsp; Also recall that a preorder traversal&nbsp;displays the value of the&nbsp;<code>node</code> first, then traverses <code>node.left</code>, then traverses <code>node.right</code>.)</em></p>

<p>&nbsp;</p>

<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">[8,5,1,7,10,12]</span>
<strong>Output: </strong><span id="example-output-1">[8,5,10,1,7,null,12]
<img alt="" src="https://assets.leetcode.com/uploads/2019/03/06/1266.png" style="height: 200px; width: 306px;"></span>
</pre>

<p>&nbsp;</p>

<p><strong>Note:</strong>&nbsp;</p>

<ol>
	<li><code>1 &lt;= preorder.length &lt;= 100</code></li>
	<li>The values of <code>preorder</code> are distinct.</li>
</ol>


**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/)

## Video Notes

![img555](https://user-images.githubusercontent.com/106215989/170565121-41c102e5-f3b2-43f3-900d-6661cc23f36e.jpg)
![img557](https://user-images.githubusercontent.com/106215989/170565125-b894aca0-6f66-4f8c-a74c-2f547c66c91a.jpg)
![img559](https://user-images.githubusercontent.com/106215989/170565126-fef31f2a-01d2-4f37-b356-014b964e200d.jpg)
![img561](https://user-images.githubusercontent.com/106215989/170565127-399f655b-18e1-40b6-b8ce-72b6bc0bf413.jpg)
![img563](https://user-images.githubusercontent.com/106215989/170565130-03709522-3838-47a4-8c6c-df5eb4913e5c.jpg)
![img565](https://user-images.githubusercontent.com/106215989/170565134-f2320d4f-e3e1-4698-b304-aaaea7fb342d.jpg)
![img567](https://user-images.githubusercontent.com/106215989/170565135-075cfbf2-2c38-4243-89be-777c967fdcd9.jpg)
![img569](https://user-images.githubusercontent.com/106215989/170565139-1cacfb80-d582-44d0-b98f-c8ee7123bc0b.jpg)
![img571](https://user-images.githubusercontent.com/106215989/170565141-3fec0604-b88f-43b0-a8ce-e46e6af92d79.jpg)
![img573](https://user-images.githubusercontent.com/106215989/170565146-da6fa2d2-be2f-404e-8e24-e85cb31f1056.jpg)
![img575](https://user-images.githubusercontent.com/106215989/170565148-e04edcf8-0160-4862-bc50-54a712d5eecb.jpg)
![img577](https://user-images.githubusercontent.com/106215989/170565151-ef3afc38-1598-4cae-bb66-3f6b9f89fa16.jpg)
![img579](https://user-images.githubusercontent.com/106215989/170565153-d1189028-b058-4e85-b25f-a7b29027a956.jpg)
![img581](https://user-images.githubusercontent.com/106215989/170565156-fe3fc070-6b95-496f-b955-c04234885996.jpg)
![img583](https://user-images.githubusercontent.com/106215989/170565157-a0516955-1dc5-4a50-8a41-b80c1f3e0b1b.jpg)
![img585](https://user-images.githubusercontent.com/106215989/170565159-9bb4b55f-a286-4e9d-bbbe-236686fe8657.jpg)
![img587](https://user-images.githubusercontent.com/106215989/170565163-75b2ae2a-a1f4-4ec8-a94c-c5cd830179f6.jpg)
![img589](https://user-images.githubusercontent.com/106215989/170565165-a9014a90-daaf-4b65-997c-bdea717c9275.jpg)
![img591](https://user-images.githubusercontent.com/106215989/170565167-401d4a97-051a-4459-a989-cab8a1aa95b9.jpg)
![img593](https://user-images.githubusercontent.com/106215989/170565169-0f06ebce-df96-4803-85f0-b41e97969339.jpg)
![img595](https://user-images.githubusercontent.com/106215989/170565171-87915cc8-f6f1-4590-a87d-b7742a1bb34e.jpg)
![img597](https://user-images.githubusercontent.com/106215989/170565174-c6512396-6b42-41b0-9c72-7c6f4671c61d.jpg)


## Solution 1.

```cpp

// OJ: https://leetcode.com/problems/construct-binary-search-tree-from-preorder-traversal/
// Time: O(N^2)
// Space: O(H)

class Solution 
{
public:
    
    TreeNode *build(vector<int> &preorder, int &i, int bound)
    {
        // If it's a out of bound and we don't have any elements to insert
        if(i==preorder.size() or preorder[i]>bound) return NULL;
        
        // Make the node at ith index
        TreeNode *root= new TreeNode(preorder[i++]);
        
        // Make the 2 recursive calls
        root->left= build(preorder, i , root->val);
        root->right= build(preorder, i, bound);
        
        // Return root
        return root;
    }
    
    TreeNode* bstFromPreorder(vector<int>& preorder) 
    {
        // Pointer i(th) for the iteration 
        int i=0;
        
        // Return the build 
        return build(preorder,i,INT_MAX);
    }
};

```

