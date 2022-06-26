# [285. Inorder Successor in BST (Medium)](https://leetcode.com/problems/inorder-successor-in-bst/)

<p>Given a binary search tree and a node in it, find the in-order successor of that node in the BST.</p>

<p><b>Note</b>: If the given node has no in-order successor in the tree, return <code>null</code>.</p>

<p><b>Example 1:</b></p>

<pre><b>Input:</b> root = <code>[2,1,3], p = 1

  2
 / \
1   3
</code>
<b>Output:</b> 2</pre>

<p><b>Example 2:</b></p>

<pre><b>Input:</b> root = <code>[5,3,6,2,4,null,null,1], p = 6

      5
     / \
    3   6
   / \
  2   4
 /   
1
</code>
<b>Output:</b> null</pre>


**Companies**:  
[Amazon](https://leetcode.com/company/amazon), [Google](https://leetcode.com/company/google), [Microsoft](https://leetcode.com/company/microsoft), [Palantir Technologies](https://leetcode.com/company/palantir-technologies), [Facebook](https://leetcode.com/company/facebook)

**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/)

**Similar Questions**:
* [Binary Tree Inorder Traversal (Medium)](https://leetcode.com/problems/binary-tree-inorder-traversal/)
* [Binary Search Tree Iterator (Medium)](https://leetcode.com/problems/binary-search-tree-iterator/)

## Video Notes

![img635](https://user-images.githubusercontent.com/106215989/170564905-fd7257a8-c7dd-49b7-9d8f-141d9ea859ac.jpg)
![img637](https://user-images.githubusercontent.com/106215989/170564910-4a5c5fe8-a797-43e1-abcc-c7e55afa9098.jpg)
![img639](https://user-images.githubusercontent.com/106215989/170564914-aed8ec23-dc45-4b3c-8983-2a1e3a92b4ac.jpg)
![img641](https://user-images.githubusercontent.com/106215989/170564916-a1ecdcd8-590a-4aa0-85e9-43819b39553e.jpg)
![img643](https://user-images.githubusercontent.com/106215989/170564923-2945469b-c8b3-4197-b3aa-4bf7598946f0.jpg)
![img645](https://user-images.githubusercontent.com/106215989/170564924-b021a76c-ec4d-4928-b213-65ea4b7842f3.jpg)
![img647](https://user-images.githubusercontent.com/106215989/170564926-72990d79-d74f-4a93-acc1-ded7d42a5dfa.jpg)
![img649](https://user-images.githubusercontent.com/106215989/170564930-27502d0f-aee2-48e8-bd17-efce2aafd797.jpg)
![img651](https://user-images.githubusercontent.com/106215989/170564933-2df3a466-90f3-487d-b4a3-00d60636d401.jpg)
![img653](https://user-images.githubusercontent.com/106215989/170564936-98c88bbf-71f3-4e14-8f29-6eb9f360d356.jpg)
![img655](https://user-images.githubusercontent.com/106215989/170564937-7a7ea915-cb3e-4aac-9dba-035ffa37cb39.jpg)
![img108](https://user-images.githubusercontent.com/106215989/170565010-0dc41b64-30b8-427e-a9c6-3800b1a60ab7.jpg)

## Solution 0.

```cpp
// OJ: https://leetcode.com/problems/inorder-successor-in-bst/
// Time: O(H)
// Space: O(1)

class Solution 
{
public:
    TreeNode* inorderSuccessor(TreeNode* root, TreeNode* p) 
    {
        TreeNode* successor = NULL;
        
        while (root != NULL) 
        {
            
            if (p->val >= root->val) 
            {
                root = root->right;
            } 
            else 
            {
                successor = root;
                root = root->left;
            }
        }
        
        return successor;
    }
};
```

## Solution 1. Recursive

```cpp
// OJ: https://leetcode.com/problems/inorder-successor-in-bst/
// Time: O(N)
// Space: O(logN)

class Solution 
{
private:
    TreeNode *target, *ans = NULL;
    bool seen = false;
    void inorder(TreeNode *root) 
    {
        if (!root) return;
        inorder(root->left);
        if (seen && !ans) ans = root;
        if (seen && ans) return;
        if (root == target) seen = true;
        inorder(root->right);
    }
public:
    TreeNode* inorderSuccessor(TreeNode* root, TreeNode* p) 
    {
        target = p;
        inorder(root);
        return ans;
    }
};
```

## Solution 2.

Solution 1 doesn't take advantage of BST. Try to find the smallest number greater than `p->val`.

```cpp
// OJ: https://leetcode.com/problems/inorder-successor-in-bst/
// Time: O(logN)
// Space: O(1)
// Ref: https://leetcode.com/problems/inorder-successor-in-bst/discuss/72721/10-(and-4)-lines-O(h)-JavaC%2B%2B

class Solution 
{
public:
    TreeNode* inorderSuccessor(TreeNode* root, TreeNode* p) 
    {
        TreeNode *best = NULL;
        while (root) 
        {
            root = root->val > p->val ? (best = root)->left : root->right;
        }
        return best;
    }
};
```

