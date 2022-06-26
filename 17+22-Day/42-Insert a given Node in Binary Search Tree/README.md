# [701. Insert into a Binary Search Tree (Medium)](https://leetcode.com/problems/insert-into-a-binary-search-tree/)

<p>You are given the <code>root</code> node of a binary search tree (BST) and a <code>value</code> to insert into the tree. Return <em>the root node of the BST after the insertion</em>. It is <strong>guaranteed</strong> that the new value does not exist in the original BST.</p>

<p><strong>Notice</strong>&nbsp;that there may exist&nbsp;multiple valid ways for the&nbsp;insertion, as long as the tree remains a BST after insertion. You can return <strong>any of them</strong>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/10/05/insertbst.jpg" style="width: 752px; height: 221px;">
<pre><strong>Input:</strong> root = [4,2,7,1,3], val = 5
<strong>Output:</strong> [4,2,7,1,3,5]
<strong>Explanation:</strong> Another accepted tree is:
<img alt="" src="https://assets.leetcode.com/uploads/2020/10/05/bst.jpg" style="width: 352px; height: 301px;">
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> root = [40,20,60,10,30,50,70], val = 25
<strong>Output:</strong> [40,20,60,10,30,50,70,null,null,25]
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> root = [4,2,7,1,3,null,null,null,null,null,null], val = 5
<strong>Output:</strong> [4,2,7,1,3,5]
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in&nbsp;the tree will be in the range <code>[0,&nbsp;10<sup>4</sup>]</code>.</li>
	<li><code>-10<sup>8</sup> &lt;= Node.val &lt;= 10<sup>8</sup></code></li>
	<li>All the values <code>Node.val</code> are <strong>unique</strong>.</li>
	<li><code>-10<sup>8</sup> &lt;= val &lt;= 10<sup>8</sup></code></li>
	<li>It's <strong>guaranteed</strong> that <code>val</code> does not exist in the original BST.</li>
</ul>


**Companies**:  
[LinkedIn](https://leetcode.com/company/linkedin), [Amazon](https://leetcode.com/company/amazon)

**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Binary Search Tree](https://leetcode.com/tag/binary-search-tree/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Search in a Binary Search Tree (Easy)](https://leetcode.com/problems/search-in-a-binary-search-tree/)

## Video Notes

![img451](https://user-images.githubusercontent.com/106215989/170555038-84f1f76b-6ede-429f-b846-c897e4e87b70.jpg)
![img453](https://user-images.githubusercontent.com/106215989/170555046-f978dfeb-2a0e-4015-8ac9-34d83b2f21b9.jpg)
![img455](https://user-images.githubusercontent.com/106215989/170555047-50489cc6-b223-44af-b65f-8f7f1220e59d.jpg)
![img457](https://user-images.githubusercontent.com/106215989/170555051-facfd556-2765-4542-97a8-51ec2d699711.jpg)
![img459](https://user-images.githubusercontent.com/106215989/170555054-de772d83-d123-4d13-a5e0-fedef8f68f15.jpg)
![img461](https://user-images.githubusercontent.com/106215989/170555056-bf85012c-b5a6-4e26-af2d-49c093275b2b.jpg)
![img463](https://user-images.githubusercontent.com/106215989/170555060-0ddcaa40-bda0-4f0c-8cf6-0b65008471d3.jpg)
![image](https://user-images.githubusercontent.com/106215989/175798635-4607dbe5-618a-4298-b9bb-924716778211.png)


## Solution 1.

```cpp
// OJ: https://leetcode.com/problems/insert-into-a-binary-search-tree/
// Time: O(H)
// Space: O(H)

class Solution 
{
public:
    TreeNode* insertIntoBST(TreeNode* root, int val) 
    {
        // If the root is empty then make a new node and return 
        if(root== NULL) return new TreeNode(val);
        
        // Take the root into the current
        TreeNode *current= root;
        
        // Iterate till root not empty
        while(true)
        {
            // If the current val is greater than right then move right
            if(current->val <= val)
            {
                // If the current is not null then move right
                if(current->right!= NULL)
                {
                    current= current->right;
                }
                
                // Else root of right is empty then make the new node
                else
                {
                    current->right= new TreeNode(val);
                    break;
                }
            }
            
            // Same process for the left tree
            else
            {
                if(current->left!= NULL)
                {
                    current= current->left;
                }
                else
                {
                    current->left= new TreeNode(val);
                    break;
                }
            }
        }
        
        // Finally return the root
        return root;
    }
};
```

## Solution 2.

```cpp
// OJ: https://leetcode.com/problems/insert-into-a-binary-search-tree/
// Time: O(H)
// Space: O(H)

class Solution 
{
public:
    TreeNode* insertIntoBST(TreeNode* root, int val) 
    {
        if (!root) return new TreeNode(val);
        if (val > root->val) root->right = insertIntoBST(root->right, val);
        else root->left = insertIntoBST(root->left, val);
        return root;
    }
};
```


