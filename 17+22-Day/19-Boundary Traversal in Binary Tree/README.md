# [545. Boundary of Binary Tree (Medium)](https://leetcode.com/problems/boundary-of-binary-tree/)

<p>The <strong>boundary</strong> of a binary tree is the concatenation of the <strong>root</strong>, the <strong>left boundary</strong>, the <strong>leaves</strong> ordered from left-to-right, and the <strong>reverse order</strong> of the <strong>right boundary</strong>.</p>

<p>The <strong>left boundary</strong> is the set of nodes defined by the following:</p>

<ul>
	<li>The root node's left child is in the left boundary. If the root does not have a left child, then the left boundary is <strong>empty</strong>.</li>
	<li>If a node in the left boundary and has a left child, then the left child is in the left boundary.</li>
	<li>If a node is in the left boundary, has <strong>no</strong> left child, but has a right child, then the right child is in the left boundary.</li>
	<li>The leftmost leaf is <strong>not</strong> in the left boundary.</li>
</ul>

<p>The <strong>right boundary</strong> is similar to the <strong>left boundary</strong>, except it is the right side of the root's right subtree. Again, the leaf is <strong>not</strong> part of the <strong>right boundary</strong>, and the <strong>right boundary</strong> is empty if the root does not have a right child.</p>

<p>The <strong>leaves</strong> are nodes that do not have any children. For this problem, the root is <strong>not</strong> a leaf.</p>

<p>Given the <code>root</code> of a binary tree, return <em>the values of its <strong>boundary</strong></em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/11/11/boundary1.jpg" style="width: 299px; height: 290px;">
<pre><strong>Input:</strong> root = [1,null,2,3,4]
<strong>Output:</strong> [1,3,4,2]
<b>Explanation:</b>
- The left boundary is empty because the root does not have a left child.
- The right boundary follows the path starting from the root's right child 2 -&gt; 4.
  4 is a leaf, so the right boundary is [2].
- The leaves from left to right are [3,4].
Concatenating everything results in [1] + [] + [3,4] + [2] = [1,3,4,2].
</pre>

<p><strong>Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/11/11/boundary2.jpg" style="width: 599px; height: 411px;">
<pre><strong>Input:</strong> root = [1,2,3,4,5,6,null,null,null,7,8,9,10]
<strong>Output:</strong> [1,2,4,7,8,9,10,6,3]
<b>Explanation:</b>
- The left boundary follows the path starting from the root's left child 2 -&gt; 4.
  4 is a leaf, so the left boundary is [2].
- The right boundary follows the path starting from the root's right child 3 -&gt; 6 -&gt; 10.
  10 is a leaf, so the right boundary is [3,6], and in reverse order is [6,3].
- The leaves from left to right are [4,7,8,9,10].
Concatenating everything results in [1] + [2] + [4,7,8,9,10] + [6,3] = [1,2,4,7,8,9,10,6,3].
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is in the range <code>[1, 10<sup>4</sup>]</code>.</li>
	<li><code>-1000 &lt;= Node.val &lt;= 1000</code></li>
</ul>


**Companies**:  
[Microsoft](https://leetcode.com/company/microsoft), [Amazon](https://leetcode.com/company/amazon), [Facebook](https://leetcode.com/company/facebook)

**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Depth-First Search](https://leetcode.com/tag/depth-first-search/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Binary Tree Right Side View (Medium)](https://leetcode.com/problems/binary-tree-right-side-view/)

## Video Notes

![img215](https://user-images.githubusercontent.com/106215989/170280270-dcf07b7b-dbd1-4695-81f0-096dc016834d.jpg)
![img217](https://user-images.githubusercontent.com/106215989/170280279-00ac1401-fd94-486f-9db7-73c37e2a672a.jpg)
![img219](https://user-images.githubusercontent.com/106215989/170280280-d1f8778b-5e03-4b7a-bb83-5e6a6c3b4e26.jpg)
![img221](https://user-images.githubusercontent.com/106215989/170280283-bbc8d4b9-24b6-4c5c-9c45-6aeb7b030cee.jpg)
![img223](https://user-images.githubusercontent.com/106215989/170280287-5618a786-7cb3-4ce0-aeb7-39e455a18382.jpg)
![img225](https://user-images.githubusercontent.com/106215989/170280289-b0e6cd6c-2d08-41bf-aa55-275c59666e79.jpg)
![img227](https://user-images.githubusercontent.com/106215989/170280293-54376063-9c9f-4362-9e6c-e2fefcfea7ea.jpg)
![img229](https://user-images.githubusercontent.com/106215989/170280296-c0ee8330-225c-4134-a501-aab3b9ee7232.jpg)
![img231](https://user-images.githubusercontent.com/106215989/170280298-572378ee-43ea-43fc-b56a-735994642b16.jpg)
![img233](https://user-images.githubusercontent.com/106215989/170280302-2c5c4056-e32b-4b22-b62d-23c6668fbe9b.jpg)
![img235](https://user-images.githubusercontent.com/106215989/170280308-ae90eb01-75a1-4eef-9714-ffcf706dcd9c.jpg)
![img237](https://user-images.githubusercontent.com/106215989/170280311-98484218-c68e-4591-9191-1560bd32c990.jpg)
![img239](https://user-images.githubusercontent.com/106215989/170280318-64c7fcaa-bbb9-478e-b746-ce82784157c3.jpg)
![img241](https://user-images.githubusercontent.com/106215989/170280321-e82b9ddb-a48d-4425-9f2d-ffac871419e1.jpg)

## Solution 2. Dfs(Gfg Solution)

```cpp

// Expected Time Complexity: O(N). 
// Expected Auxiliary Space: O(Height of the Tree).

class Solution 
{
public:

    void travel_left_boundary(Node *root, vector<int> &ans)
    {
        // Base case
        if((root==NULL) or (root->left==NULL and root->right == NULL) ) return ;
        ans.push_back(root->data);
        
        // If left exists then go to the left side
        if(root->left)  travel_left_boundary(root->left,ans);
    
        // If right exists then go to the right side
        else travel_left_boundary(root->right,ans);
    }
    
    void travel_leaf(Node* root,vector<int>& ans)
    {
        // Base case check 
        if(root == NULL) return;
    
        // If no left and right child
        if(root->left == NULL && root->right == NULL)
        {
            ans.push_back(root->data);
            return;
        }
        
        // 2 Recursvie calls 
        travel_leaf(root->left,ans);
        travel_leaf(root->right,ans);
        
    }

    void travel_right_boundary(Node *root, vector<int> &ans)
    {
        // Base case
        if((root==NULL) or (root->left==NULL and root->right == NULL) ) return ;
        
        // If right exists then go to the right side
        if(root->right)  travel_right_boundary(root->right,ans);
    
        // If left exists then go to the left side
        else travel_right_boundary(root->left,ans);
        
        ans.push_back(root->data);
    }
    
    vector <int> boundary(Node *root)
    {
        vector<int > ans;
        if(root==NULL) return ans;
        ans.push_back(root->data);
        
        // Step 1: Travel the left boundary
        travel_left_boundary(root->left,ans);
        
        // Step 2: Travel the left and right subtree
        travel_leaf(root->left, ans);
        travel_leaf(root->right,ans);
        
        // Step 3 Travel the right boundary
        travel_right_boundary(root->right,ans);
        
        // Finally return the ans
        return ans;
    }
};

```

## Solution 2. DFS

```cpp
// OJ: https://leetcode.com/problems/boundary-of-binary-tree/
// Time: O(N)
// Space: O(H)

class Solution 
{
    vector<int> ans, right;
    void dfs(TreeNode *node, int state) { // 1 left boundary, 2 right boundary, 0 otherwise
        if (!node) return;
        if (state == 1) ans.push_back(node->val);
        else if (state == 2) right.push_back(node->val);
        else if (!node->left && !node->right) ans.push_back(node->val);
        dfs(node->left, state == 1 ? 1 : (state == 2 && !node->right ? 2 : 0));
        dfs(node->right, state == 2 ? 2 : (state == 1 && !node->left ? 1 : 0));
    }
public:
    vector<int> boundaryOfBinaryTree(TreeNode* root) 
    {
        ans.push_back(root->val);
        dfs(root->left, 1);
        dfs(root->right, 2);
        for (int i = right.size() - 1; i >= 0; --i) ans.push_back(right[i]);
        return ans;
    }
};
```


