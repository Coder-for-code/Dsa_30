# [230. Kth Smallest Element in a BST (Medium)](https://leetcode.com/problems/kth-smallest-element-in-a-bst/)

<p>Given the <code>root</code> of a binary search tree, and an integer <code>k</code>, return <em>the</em> <code>k<sup>th</sup></code> <em>smallest value (<strong>1-indexed</strong>) of all the values of the nodes in the tree</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2021/01/28/kthtree1.jpg" style="width: 212px; height: 301px;">
<pre><strong>Input:</strong> root = [3,1,4,null,2], k = 1
<strong>Output:</strong> 1
</pre>

<p><strong>Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2021/01/28/kthtree2.jpg" style="width: 382px; height: 302px;">
<pre><strong>Input:</strong> root = [5,3,6,2,4,null,null,1], k = 3
<strong>Output:</strong> 3
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is <code>n</code>.</li>
	<li><code>1 &lt;= k &lt;= n &lt;= 10<sup>4</sup></code></li>
	<li><code>0 &lt;= Node.val &lt;= 10<sup>4</sup></code></li>
</ul>

<p>&nbsp;</p>
<p><strong>Follow up:</strong> If the BST is modified often (i.e., we can do insert and delete operations) and you need to find the kth smallest frequently, how would you optimize?</p>


**Companies**:  
[Amazon](https://leetcode.com/company/amazon), [Uber](https://leetcode.com/company/uber), [Facebook](https://leetcode.com/company/facebook)

**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Depth-First Search](https://leetcode.com/tag/depth-first-search/), [Binary Search Tree](https://leetcode.com/tag/binary-search-tree/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Binary Tree Inorder Traversal (Easy)](https://leetcode.com/problems/binary-tree-inorder-traversal/)
* [Second Minimum Node In a Binary Tree (Easy)](https://leetcode.com/problems/second-minimum-node-in-a-binary-tree/)

## Video Notes

![img503](https://user-images.githubusercontent.com/106215989/170555535-375b8cde-52f2-4f8e-9a43-e7c9bd1b6ce6.jpg)
![img505](https://user-images.githubusercontent.com/106215989/170555537-572fc2bc-1daf-431f-a178-d30d8147e524.jpg)
![img507](https://user-images.githubusercontent.com/106215989/170555540-76b541cf-a9df-4a3c-b649-68a388354971.jpg)
![img509](https://user-images.githubusercontent.com/106215989/170555541-46a06f4e-b466-4a35-8b10-c7748447e371.jpg)
![img511](https://user-images.githubusercontent.com/106215989/170555543-eb656dac-12ad-40e3-a917-f81a3d9c1ea3.jpg)
![img513](https://user-images.githubusercontent.com/106215989/170555546-800ee7b2-e4ac-4fc9-b9ed-138de667a766.jpg)
![img515](https://user-images.githubusercontent.com/106215989/170555548-b87bd2b1-a150-4017-b6d6-debed9b8e3e1.jpg)
![img517](https://user-images.githubusercontent.com/106215989/170555551-b6e76da7-b515-4820-8b9e-05b25b54fc92.jpg)
![img519](https://user-images.githubusercontent.com/106215989/170555554-33f4d54f-6a09-402a-90ca-6a468f1ed095.jpg)
![img521](https://user-images.githubusercontent.com/106215989/170555556-d40111a2-8bc1-4658-88f4-42290fb6ce20.jpg)
![img523](https://user-images.githubusercontent.com/106215989/170555558-5b5ed415-bbff-4fdf-a86b-2028ba1593d5.jpg)
![img525](https://user-images.githubusercontent.com/106215989/170555561-6d443f75-11e1-40ce-a302-07e4966e1155.jpg)
![img527](https://user-images.githubusercontent.com/106215989/170555566-64399a10-d02b-48e8-a66e-681a510d6241.jpg)
![img529](https://user-images.githubusercontent.com/106215989/170555567-a473319d-49c1-44c3-9c3c-418fcfcbe3e8.jpg)
![img531](https://user-images.githubusercontent.com/106215989/170555571-3c306111-a3ed-41df-973e-639ce30a3a54.jpg)
![img533](https://user-images.githubusercontent.com/37560890/170561908-0e6e3616-1413-47b1-b661-8ca90b738996.jpg)
![image](https://user-images.githubusercontent.com/37560890/175804462-7cab4fc0-a450-415e-8ee3-c7deeb43fa44.png)


## Solution 1.

```cpp
// OJ: https://leetcode.com/problems/kth-smallest-element-in-a-bst/
// Time: O(N)
// Space: O(H)

class Solution 
{
public:
        // Initialize the variables value and answer
        int value;
        int ans;
        
        // Helper method for the following function
        void helper_method(TreeNode *root)
        {
            // If the root is null then return 
            if(root==NULL) return;
            
            // Since it's a smallest go to the left subtree
            helper_method(root->left);
            
            // Reduce the value of the k
            value--;
            
            // If the value of k is 0 then return the root of value
            if(value ==0)
            {
                ans= root->val;
            }
            
            // If on the left subtree right exits then go the left of right
            helper_method(root->right);
            
        }
        
        int kthSmallest(TreeNode* root, int k) 
        {
            // Take the value of the k into value
            value= k;
            
            // Calling the helper method
            helper_method(root);
            
            // Return the ans
            return ans;
        }
};

```

## Solution 2. In-order traversal (Iterative)

```cpp
// OJ: https://leetcode.com/problems/kth-smallest-element-in-a-bst/
// Time: O(N)
// Space: O(H)

class Solution 
{
public:
    int kthSmallest(TreeNode* root, int k) 
    {
        stack<TreeNode*> s;
        while (root || s.size()) 
        {
            while (root) 
            {
                s.push(root);
                root = root->left;
            }
            root = s.top();
            s.pop();
            if (--k == 0) return root->val;
            root = root->right;
        }
        return -1;
    }
};
```

