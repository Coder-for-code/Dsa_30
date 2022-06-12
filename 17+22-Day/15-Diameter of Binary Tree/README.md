# [543. Diameter of Binary Tree (Easy)](https://leetcode.com/problems/diameter-of-binary-tree/)

<p>Given the <code>root</code> of a binary tree, return <em>the length of the <strong>diameter</strong> of the tree</em>.</p>

<p>The <strong>diameter</strong> of a binary tree is the <strong>length</strong> of the longest path between any two nodes in a tree. This path may or may not pass through the <code>root</code>.</p>

<p>The <strong>length</strong> of a path between two nodes is represented by the number of edges between them.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2021/03/06/diamtree.jpg" style="width: 292px; height: 302px;">
<pre><strong>Input:</strong> root = [1,2,3,4,5]
<strong>Output:</strong> 3
<strong>Explanation:</strong> 3 is the length of the path [4,2,1,3] or [5,2,1,3].
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> root = [1,2]
<strong>Output:</strong> 1
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is in the range <code>[1, 10<sup>4</sup>]</code>.</li>
	<li><code>-100 &lt;= Node.val &lt;= 100</code></li>
</ul>


**Companies**:  
[Facebook](https://leetcode.com/company/facebook), [Amazon](https://leetcode.com/company/amazon), [Google](https://leetcode.com/company/google), [Microsoft](https://leetcode.com/company/microsoft), [Bloomberg](https://leetcode.com/company/bloomberg), [Apple](https://leetcode.com/company/apple), [Adobe](https://leetcode.com/company/adobe), [Tesla](https://leetcode.com/company/tesla), [Intuit](https://leetcode.com/company/intuit)

**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Depth-First Search](https://leetcode.com/tag/depth-first-search/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Diameter of N-Ary Tree (Medium)](https://leetcode.com/problems/diameter-of-n-ary-tree/)


## Video Notes


![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0134](https://user-images.githubusercontent.com/106215989/170276292-5299cdd6-6381-4536-8803-fbb64a64a561.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0135](https://user-images.githubusercontent.com/106215989/170276301-cd9ad1c1-42d3-4074-a1e6-ec81ff5e47d3.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0136](https://user-images.githubusercontent.com/106215989/170276305-f28c2f6b-1229-4722-ac70-b48ad1e56505.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0137](https://user-images.githubusercontent.com/106215989/170276306-2807af3d-d6b5-4a6e-835d-bfb2e0600db5.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0138](https://user-images.githubusercontent.com/106215989/170276307-38b46a1e-e292-43cc-972d-2b1d0a968236.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0139](https://user-images.githubusercontent.com/106215989/170276309-9ea85ce6-46ab-45a2-b9eb-8cec543be94a.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0140](https://user-images.githubusercontent.com/106215989/170276314-6d79fada-ab4f-4768-8a99-0be0da6cb123.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0141](https://user-images.githubusercontent.com/106215989/170276317-2a83065c-0a3b-45dc-9549-5f6520ad8f7c.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0142](https://user-images.githubusercontent.com/106215989/170276318-d48c3f80-c672-44ca-afe6-03ac41bcee38.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0143](https://user-images.githubusercontent.com/106215989/170276320-7afdcefe-22de-424e-9b3f-74221cb67397.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0144](https://user-images.githubusercontent.com/106215989/170276323-7c6ee9fd-58d5-413e-a19b-12344ebd02fe.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0145](https://user-images.githubusercontent.com/106215989/170276325-29851986-d8ea-4a36-a986-5949064b7204.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0146](https://user-images.githubusercontent.com/106215989/170276327-da7609e5-9211-4e01-a255-9f7586bc90ba.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0147](https://user-images.githubusercontent.com/106215989/170276329-0f1965c2-779b-4f6c-8409-9c368653a809.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0148](https://user-images.githubusercontent.com/106215989/170276330-5c947198-a04f-4a70-b276-fd6c0d23f8ec.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0149](https://user-images.githubusercontent.com/106215989/170276333-bd3a29e0-d011-4979-a423-018e6f88e1c0.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0150](https://user-images.githubusercontent.com/106215989/170276336-00e67b7a-3293-4083-9364-d8ae3a6ecf3f.jpg)



## Solution 1. Post-order traversal

```cpp
// OJ: https://leetcode.com/problems/diameter-of-binary-tree/
// Time: O(N)
// Space: O(H)

class Solution 
{
    int ans = 0;
    int postorder(TreeNode *root) 
    {
        if (!root) return 0;
        int left = postorder(root->left), right = postorder(root->right);
        ans = max(ans, left + right);
        return 1 + max(left, right);
    }
public:
    int diameterOfBinaryTree(TreeNode* root) 
    {
        postorder(root);
        return ans;
    }
};
```

## Solution 2. Height code simple modification

```cpp
// OJ: https://leetcode.com/problems/diameter-of-binary-tree/
// Tc: O(n)
// Sc: O(h)

class Solution 
{
public:
    
    // Helper function
    int diameter(TreeNode *root,int &ans)
    {
        // If a leaf node then return 0
        if(root==NULL)
            return 0;
        
        // Compute the left and right height
        int x=diameter(root->left,ans);
        int y=diameter(root->right,ans);
    
        // Answer variable to store the maxi diameter
        ans=max(ans,x+y);
      
        // Return height 
        return max(x,y)+1;
    }
    
    int diameterOfBinaryTree(TreeNode* root) 
    {
        int ans=0;
        diameter(root,ans);
        return ans;
    }
};
```
