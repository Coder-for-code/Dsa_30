# [653. Two Sum IV - Input is a BST (Easy)](https://leetcode.com/problems/two-sum-iv-input-is-a-bst/)

<p>Given the <code>root</code> of a Binary Search Tree and a target number <code>k</code>, return <em><code>true</code> if there exist two elements in the BST such that their sum is equal to the given target</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/09/21/sum_tree_1.jpg" style="width: 562px; height: 322px;">
<pre><strong>Input:</strong> root = [5,3,6,2,4,null,7], k = 9
<strong>Output:</strong> true
</pre>

<p><strong>Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/09/21/sum_tree_2.jpg" style="width: 562px; height: 322px;">
<pre><strong>Input:</strong> root = [5,3,6,2,4,null,7], k = 28
<strong>Output:</strong> false
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> root = [2,1,3], k = 4
<strong>Output:</strong> true
</pre>

<p><strong>Example 4:</strong></p>

<pre><strong>Input:</strong> root = [2,1,3], k = 1
<strong>Output:</strong> false
</pre>

<p><strong>Example 5:</strong></p>

<pre><strong>Input:</strong> root = [2,1,3], k = 3
<strong>Output:</strong> true
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is in the range <code>[1, 10<sup>4</sup>]</code>.</li>
	<li><code>-10<sup>4</sup>&nbsp;&lt;= Node.val &lt;= 10<sup>4</sup></code></li>
	<li><code>root</code> is guaranteed to be a <strong>valid</strong> binary search tree.</li>
	<li><code>-10<sup>5</sup>&nbsp;&lt;= k &lt;= 10<sup>5</sup></code></li>
</ul>


**Companies**:  
[Microsoft](https://leetcode.com/company/microsoft)

**Related Topics**:  
[Hash Table](https://leetcode.com/tag/hash-table/), [Two Pointers](https://leetcode.com/tag/two-pointers/), [Tree](https://leetcode.com/tag/tree/), [Depth-First Search](https://leetcode.com/tag/depth-first-search/), [Breadth-First Search](https://leetcode.com/tag/breadth-first-search/), [Binary Search Tree](https://leetcode.com/tag/binary-search-tree/), [Binary Tree](https://leetcode.com/tag/binary-tree/)

**Similar Questions**:
* [Two Sum (Easy)](https://leetcode.com/problems/two-sum/)
* [Two Sum II - Input array is sorted (Easy)](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)
* [Two Sum III - Data structure design (Easy)](https://leetcode.com/problems/two-sum-iii-data-structure-design/)
* [Two Sum BSTs (Medium)](https://leetcode.com/problems/two-sum-bsts/)

## Video Notes

![img150](https://user-images.githubusercontent.com/37560890/170563404-616f4394-36be-4116-8742-b97c06ccfae5.jpg)
![img152](https://user-images.githubusercontent.com/37560890/170563409-808c8825-ca0d-419c-86e0-913605a1a502.jpg)
![img154](https://user-images.githubusercontent.com/37560890/170563410-1bd9884d-0af5-46ab-ba55-ceadae307297.jpg)
![img156](https://user-images.githubusercontent.com/37560890/170563413-ecaf9087-79ad-4acb-8684-97f2eac269ef.jpg)
![img158](https://user-images.githubusercontent.com/37560890/170563417-eb220bb9-9525-4b28-9438-a1091308b656.jpg)
![img160](https://user-images.githubusercontent.com/37560890/170563421-3f486b6f-ecd0-4a34-905b-d37533be6db2.jpg)
![img162](https://user-images.githubusercontent.com/37560890/170563424-1b3a90fb-e32a-4609-b561-5b0eb723af74.jpg)
![img164](https://user-images.githubusercontent.com/37560890/170563428-73436afc-ca74-4f08-ac19-8f4afb498931.jpg)
![img166](https://user-images.githubusercontent.com/37560890/170563429-fdb0a90f-4651-4683-88d2-789c342c8cbe.jpg)
![img168](https://user-images.githubusercontent.com/37560890/170563432-8346e630-3e9b-45bc-b793-bfb923b5dffa.jpg)
![img170](https://user-images.githubusercontent.com/37560890/170563434-0518ddaf-fd3e-4ebb-80e8-475c2c2899ad.jpg)
![img172](https://user-images.githubusercontent.com/37560890/170563436-955870f9-fac8-4014-abec-2b5978dd27be.jpg)
![img174](https://user-images.githubusercontent.com/37560890/170563439-5086927f-6876-408a-9e75-733ef1408025.jpg)
![img176](https://user-images.githubusercontent.com/37560890/170563442-144ce34d-e316-4c8b-bd80-cb48a0eec72e.jpg)
![img178](https://user-images.githubusercontent.com/37560890/170563445-ff7715e3-33af-468b-9496-9e5793d9ca9d.jpg)
![img180](https://user-images.githubusercontent.com/37560890/170563448-ec6e94a6-525d-44cb-bbf3-bb54d5d277cd.jpg)
![img182](https://user-images.githubusercontent.com/37560890/170563450-f3f8e43e-2e67-4275-b176-e18eabbbff7e.jpg)
![img184](https://user-images.githubusercontent.com/37560890/170563452-71b60440-9f80-4fd9-b502-ea5820c8b294.jpg)
![img186](https://user-images.githubusercontent.com/37560890/170563455-13604bfb-19a9-4d12-9cae-e137d6ad8aa5.jpg)
![img188](https://user-images.githubusercontent.com/37560890/170563458-22cc86fd-d3ef-4d8f-930c-61f3262677ee.jpg)
![img190](https://user-images.githubusercontent.com/37560890/170563459-5fc73b1c-d6b1-495c-bd2b-05047728f2c2.jpg)
![img192](https://user-images.githubusercontent.com/37560890/170563461-301ca812-4ae0-4309-b659-ae182d63a142.jpg)
![img194](https://user-images.githubusercontent.com/37560890/170563464-d4222488-9713-4160-8357-4c87245ec95f.jpg)
![img196](https://user-images.githubusercontent.com/37560890/170563467-e4c71d85-7552-4b06-b6f2-adb303c131a6.jpg)
![img198](https://user-images.githubusercontent.com/37560890/170563472-3d8d8cdb-c386-436f-a502-4784c3ad11d7.jpg)


## Solution 1. BSTIterator + Two Pointers

```cpp
// OJ: https://leetcode.com/problems/two-sum-iv-input-is-a-bst/
// Time: O(N)
// Space: O(N)

class BSTIterator
{
    // Create the stack for pushing the element's
    stack<TreeNode *> s;
    
    // Make a revers variable
    // reverse true= before;
    // reverse false= next;
    bool reverse= true;
    
    public:
    
        // Returns the Bst Iterator 
        BSTIterator(TreeNode *root, bool isReverse)
        {
            reverse= isReverse;
         
            // Calling the method pushall
            pushAll(root);
        }
    
        // Checks whether the stack has elements or not
        bool hasNext()
        {
            return !s.empty();
        }
    
        // Returns the next element from the stack 
        int next()
        {
            TreeNode *tempnode= s.top();
            s.pop();
            if(!reverse) pushAll(tempnode->right);
            else pushAll(tempnode->left);
            return tempnode->val;
        }
    
    private:
        // Push all method implementation
        void pushAll(TreeNode *node)
        {
            for(;node != NULL;)
            {
                s.push(node);
                if(reverse== true)
                {
                    node= node->right;
                }
                
                else
                {
                    node= node->left;
                }
            }
        }
};


class Solution 
{
public:
    
    // 2 sum logic
    bool findTarget(TreeNode* root, int k) 
    {
        if(!root) return false;
        BSTIterator left(root,false);
        BSTIterator right(root,true);
        
        int i= left.next();
        int j= right.next();
        
        while(i<j)
        {
            if(i+j== k) return true;
            else if(i+j<k) i= left.next();
            else j= right.next();
        }
        return false;
    }
};
```

## Solution 2. Preorder Traversal + Unordered Set

This solution doesn't leverage the nature of the BST. It's a two sum solution using an `unordered_set`.

```cpp
// OJ: https://leetcode.com/problems/two-sum-iv-input-is-a-bst/
// Time: O(N)
// Space: O(N)

class Solution 
{
    unordered_set<int> s;
public:
    bool findTarget(TreeNode* root, int k) 
    {
        if (!root) return false;
        if (s.count(k - root->val)) return true;
        s.insert(root->val);
        return findTarget(root->left, k) || findTarget(root->right, k);
    }
};
```

## Solution 3. Inorder Traversal + Two Pointers

```cpp
// OJ: https://leetcode.com/problems/two-sum-iv-input-is-a-bst/
// Time: O(N)
// Space: O(N)

class Solution 
{
private:
    vector<int> v;
    void inorder(TreeNode *root) 
    {
        if (!root) return;
        inorder(root->left);
        v.push_back(root->val);
        inorder(root->right);
    }
public:
    bool findTarget(TreeNode* root, int k) 
    {
        inorder(root);
        int i = 0, j = v.size() - 1;
        while (i < j) 
        {
            int sum = v[i] + v[j];
            if (sum == k) return true;
            if (sum > k) --j;
            else ++i;
        }
        return false;
    }
};
```
