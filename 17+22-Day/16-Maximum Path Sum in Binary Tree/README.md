# [124. Binary Tree Maximum Path Sum (Hard)](https://leetcode.com/problems/binary-tree-maximum-path-sum/)

<p>A <strong>path</strong> in a binary tree is a sequence of nodes where each pair of adjacent nodes in the sequence has an edge connecting them. A node can only appear in the sequence <strong>at most once</strong>. Note that the path does not need to pass through the root.</p>

<p>The <strong>path sum</strong> of a path is the sum of the node's values in the path.</p>

<p>Given the <code>root</code> of a binary tree, return <em>the maximum <strong>path sum</strong> of any <strong>non-empty</strong> path</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/10/13/exx1.jpg" style="width: 322px; height: 182px;">
<pre><strong>Input:</strong> root = [1,2,3]
<strong>Output:</strong> 6
<strong>Explanation:</strong> The optimal path is 2 -&gt; 1 -&gt; 3 with a path sum of 2 + 1 + 3 = 6.
</pre>

<p><strong>Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/10/13/exx2.jpg">
<pre><strong>Input:</strong> root = [-10,9,20,null,null,15,7]
<strong>Output:</strong> 42
<strong>Explanation:</strong> The optimal path is 15 -&gt; 20 -&gt; 7 with a path sum of 15 + 20 + 7 = 42.
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is in the range <code>[1, 3 * 10<sup>4</sup>]</code>.</li>
	<li><code>-1000 &lt;= Node.val &lt;= 1000</code></li>
</ul>


**Companies**:  
[Facebook](https://leetcode.com/company/facebook), [DoorDash](https://leetcode.com/company/doordash), [Amazon](https://leetcode.com/company/amazon), [Google](https://leetcode.com/company/google), [Microsoft](https://leetcode.com/company/microsoft), [Adobe](https://leetcode.com/company/adobe), [Samsung](https://leetcode.com/company/samsung), [Bloomberg](https://leetcode.com/company/bloomberg), [ByteDance](https://leetcode.com/company/bytedance), [Myntra](https://leetcode.com/company/myntra), [Flipkart](https://leetcode.com/company/flipkart)

**Related Topics**:  
[Dynamic Programming](https://leetcode.com/tag/dynamic-programming/), [Tree](https://leetcode.com/tag/tree/), [Depth-First Search](https://leetcode.com/tag/depth-first-search/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Path Sum (Easy)](https://leetcode.com/problems/path-sum/)
* [Sum Root to Leaf Numbers (Medium)](https://leetcode.com/problems/sum-root-to-leaf-numbers/)
* [Path Sum IV (Medium)](https://leetcode.com/problems/path-sum-iv/)
* [Longest Univalue Path (Medium)](https://leetcode.com/problems/longest-univalue-path/)
* [Time Needed to Inform All Employees (Medium)](https://leetcode.com/problems/time-needed-to-inform-all-employees/)


## Video Notes

![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0151](https://user-images.githubusercontent.com/106215989/170276606-32b52095-1aac-431b-918f-b868c8c754cd.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0152](https://user-images.githubusercontent.com/106215989/170276614-91c717c5-db44-4517-b441-445219bbaf68.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0153](https://user-images.githubusercontent.com/106215989/170276615-fe4f5175-fd31-4994-ac01-a36f40fcf9c2.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0154](https://user-images.githubusercontent.com/106215989/170276617-ff37cbb3-e56a-4232-97f5-c7066bd8d2bc.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0155](https://user-images.githubusercontent.com/106215989/170276621-e23b4cb0-f77f-48ef-8b3d-0833e1185096.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0156](https://user-images.githubusercontent.com/106215989/170276623-74bb1a35-ece3-403a-bd48-1e4c62e47116.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0157](https://user-images.githubusercontent.com/106215989/170276626-e160aca9-a8d9-49b5-880e-d48836e04bbf.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0158](https://user-images.githubusercontent.com/106215989/170276628-2a82a48e-1054-4693-928b-507f4af459fd.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0159](https://user-images.githubusercontent.com/106215989/170276630-3d943689-d9e3-4a70-b638-5956b0617d56.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0160](https://user-images.githubusercontent.com/106215989/170276634-9fe73ee2-a9b7-4dfe-a68a-89b2466814d0.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0161](https://user-images.githubusercontent.com/106215989/170276635-efda9649-c3aa-4a03-ab50-ede189654274.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0162](https://user-images.githubusercontent.com/106215989/170276639-21f39a5b-0421-4494-a923-4199af5eefda.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0163](https://user-images.githubusercontent.com/106215989/170276646-f551d40d-e522-46a2-8178-5edbcb4b6c42.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0164](https://user-images.githubusercontent.com/106215989/170276652-cacf9521-365d-4a1b-9f7d-8701cd9e03b6.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0165](https://user-images.githubusercontent.com/106215989/170276655-6013161c-d016-4dec-b4e8-6a1e64b353e9.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0166](https://user-images.githubusercontent.com/106215989/170276658-4a932d1b-6dde-480c-8b87-d39d747b4463.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0167](https://user-images.githubusercontent.com/106215989/170276661-76e8f944-33eb-4b24-9c86-eefaa08dbeb9.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0168](https://user-images.githubusercontent.com/106215989/170276664-bc951268-6b17-4ecf-b4f8-ded36f499483.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0169](https://user-images.githubusercontent.com/106215989/170276666-2403882c-6007-4a82-abc1-8147ca37d8ee.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0170](https://user-images.githubusercontent.com/106215989/170276670-31fda61e-0b63-4fbb-abb0-5bb5eeea6efe.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0171](https://user-images.githubusercontent.com/106215989/170276674-4c83110b-ea63-4ce3-838b-4238a1a055aa.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0172](https://user-images.githubusercontent.com/106215989/170276676-9b56da2e-1bb4-43f7-9888-642164748bb9.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0173](https://user-images.githubusercontent.com/106215989/170276678-4a408113-776f-45b4-867d-b07294919185.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0174](https://user-images.githubusercontent.com/106215989/170276682-b4adc6d0-174a-41c1-91b9-460a5ffece7f.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0175](https://user-images.githubusercontent.com/106215989/170276686-ffad03dc-a4f5-491d-ba6a-b4b4af279402.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0176](https://user-images.githubusercontent.com/106215989/170276691-1e30fcb7-ae24-42e8-aa89-4aa589396e9c.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0177](https://user-images.githubusercontent.com/106215989/170276694-6b0af92c-cbbd-487d-b371-0ba7f5bf0cd8.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0178](https://user-images.githubusercontent.com/106215989/170276700-9776cd2a-56fb-4b58-b777-479eb458525d.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0179](https://user-images.githubusercontent.com/106215989/170276701-646a2dc4-e733-4cfa-b9c4-2dc19d9c5a99.jpg)


## Solution 1. Post-order traversal

For node `n`, let `f(n)` be the maximum path sum that STARTS from node `n` to its children. It means that the path can only go through one of its children, not both of them. We have:

```
f(n) = n->val + max({ 0, f(n->left), f(n->right) })
```

For each node `n`, we also need to try to update the maximum path sum using `n->val + max(0, f(n->left)) + max(0, f(n->right))`.

In sum, we can use post order traversal to compute `f(n)` and update maximum path sum along the process.

```cpp
// OJ: https://leetcode.com/problems/binary-tree-maximum-path-sum/
// Time: O(N)
// Space: O(H)

class Solution 
{
    int ans = INT_MIN;
    int dfs(TreeNode *root) 
    {
        if (!root) return 0;
        int left = dfs(root->left), right = dfs(root->right);
        ans = max(ans, root->val + left + right);
        return max(0, root->val + max(left, right));
    }
public:
    int maxPathSum(TreeNode* root) 
    {
        dfs(root);
        return ans;
    }
};
```


