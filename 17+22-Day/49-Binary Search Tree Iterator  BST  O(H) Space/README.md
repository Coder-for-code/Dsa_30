# [173. Binary Search Tree Iterator (Medium)](https://leetcode.com/problems/binary-search-tree-iterator/)

<p>Implement an iterator over a binary search tree (BST). Your iterator will be initialized with the root node of a BST.</p>

<p>Calling <code>next()</code> will return the next smallest number in the BST.</p>

<p>&nbsp;</p>

<ul>
</ul>

<p><strong>Example:</strong></p>

<p><strong><img alt="" src="https://assets.leetcode.com/uploads/2018/12/25/bst-tree.png" style="width: 189px; height: 178px;"></strong></p>

<pre>BSTIterator iterator = new BSTIterator(root);
iterator.next();    // return 3
iterator.next();    // return 7
iterator.hasNext(); // return true
iterator.next();    // return 9
iterator.hasNext(); // return true
iterator.next();    // return 15
iterator.hasNext(); // return true
iterator.next();    // return 20
iterator.hasNext(); // return false
</pre>

<p>&nbsp;</p>

<p><b>Note:</b></p>

<ul>
	<li><code>next()</code> and <code>hasNext()</code> should run in average O(1) time and uses O(<i>h</i>) memory, where <i>h</i> is the height of the tree.</li>
	<li>You may assume that&nbsp;<code>next()</code>&nbsp;call&nbsp;will always be valid, that is, there will be at least a next smallest number in the BST when <code>next()</code> is called.</li>
</ul>


**Companies**:  
[Facebook](https://leetcode.com/company/facebook), [Amazon](https://leetcode.com/company/amazon), [Microsoft](https://leetcode.com/company/microsoft), [Oracle](https://leetcode.com/company/oracle), [Bloomberg](https://leetcode.com/company/bloomberg), [Qualtrics](https://leetcode.com/company/qualtrics), [Cloudera](https://leetcode.com/company/cloudera), [Uber](https://leetcode.com/company/uber), [Google](https://leetcode.com/company/google), [LinkedIn](https://leetcode.com/company/linkedin), [Cisco](https://leetcode.com/company/cisco)

**Related Topics**:  
[Stack](https://leetcode.com/tag/stack/), [Tree](https://leetcode.com/tag/tree/), [Design](https://leetcode.com/tag/design/)

**Similar Questions**:
* [Binary Tree Inorder Traversal (Medium)](https://leetcode.com/problems/binary-tree-inorder-traversal/)
* [Flatten 2D Vector (Medium)](https://leetcode.com/problems/flatten-2d-vector/)
* [Zigzag Iterator (Medium)](https://leetcode.com/problems/zigzag-iterator/)
* [Peeking Iterator (Medium)](https://leetcode.com/problems/peeking-iterator/)
* [Inorder Successor in BST (Medium)](https://leetcode.com/problems/inorder-successor-in-bst/)

## Video Notes

![img110](https://user-images.githubusercontent.com/37560890/170564027-79a0646b-4922-4bbe-8925-91956604f350.jpg)
![img112](https://user-images.githubusercontent.com/37560890/170564038-f3e25847-1180-416f-a561-ae2ab7ab8c4b.jpg)
![img114](https://user-images.githubusercontent.com/37560890/170564042-3af24a1d-e129-49d5-83af-4cacab319bde.jpg)
![img116](https://user-images.githubusercontent.com/37560890/170564043-2ee1c0f2-6921-4b86-be93-38c3ef08f123.jpg)
![img118](https://user-images.githubusercontent.com/106215989/170564081-b4258487-f8b7-4560-87c9-58ac2353380c.jpg)
![img120](https://user-images.githubusercontent.com/106215989/170564090-51eaecf6-af6b-4d22-9679-b4cb41a5df32.jpg)
![img122](https://user-images.githubusercontent.com/106215989/170564094-c17841e2-7e25-4120-8e3e-4c3317e5aeab.jpg)
![img124](https://user-images.githubusercontent.com/106215989/170564095-29a12795-07ea-4c4f-899a-fb163b35fe7a.jpg)
![img126](https://user-images.githubusercontent.com/106215989/170564097-e7c1cce0-a75f-42ff-ac1d-40b2d35c17b9.jpg)
![img128](https://user-images.githubusercontent.com/106215989/170564100-f5e82f46-f1c4-4e38-827f-3405158af99d.jpg)
![img130](https://user-images.githubusercontent.com/106215989/170564102-95017f3b-96cc-4377-bd24-dac6b559c5dd.jpg)
![img132](https://user-images.githubusercontent.com/106215989/170564105-e33ba61c-4e9b-4c34-93d6-d5dddbad9e3f.jpg)
![img134](https://user-images.githubusercontent.com/106215989/170564106-fd485074-a483-4d32-bd98-726515111826.jpg)
![img136](https://user-images.githubusercontent.com/106215989/170564108-2e1b78a6-6845-42a9-9f99-b066bdb8bb45.jpg)
![img138](https://user-images.githubusercontent.com/106215989/170564110-6a128fdd-8ba7-4338-a3a0-dba4392bdbc8.jpg)
![img140](https://user-images.githubusercontent.com/106215989/170564112-eac30e8e-6763-4707-b5bd-b3d81b308314.jpg)
![img142](https://user-images.githubusercontent.com/106215989/170564117-62637c98-5f6d-4140-ace3-f4a55afb34a8.jpg)
![img144](https://user-images.githubusercontent.com/106215989/170564121-21a3edae-91c3-4870-9739-da7b69fdf634.jpg)
![img146](https://user-images.githubusercontent.com/106215989/170564125-afab7b6b-c3c4-4609-b04d-edd2c733be47.jpg)
![img148](https://user-images.githubusercontent.com/106215989/170564129-a614e2b1-d2f0-42f0-bbb4-15af1e28cb7a.jpg)
![image](https://user-images.githubusercontent.com/37560890/175847835-3738e352-b09f-4fa2-8645-48ee8708555b.png)

## Solution 1. Stack

```cpp
// OJ: https://leetcode.com/problems/binary-search-tree-iterator/
// Time: O(1) amortized
// Space: O(H)

class BSTIterator
{
private:
    stack<TreeNode*> s;
    void pushNodes(TreeNode *node) 
    {
        while (node) 
        {
            s.push(node);
            node = node->left;
        }
    }
public:
    BSTIterator(TreeNode* root) 
    {
        pushNodes(root);
    }
    
    int next() 
    {
        auto node = s.top();
        s.pop();
        pushNodes(node->right);
        return node->val;
    }
    
    bool hasNext() 
    {
        return s.size();
    }
};
```

## Solution 2. 

```cpp
// OJ: https://leetcode.com/problems/binary-search-tree-iterator/
// Time: O(1) amortized
// Space: O(H)


class BSTIterator 
{
    // Make a stack for pushing the element's
    private: stack<TreeNode * > s;
    
    public:
    // Bst iterator function
    BSTIterator(TreeNode* root) 
    {
        // Calling the push all method
        push_All(root);  
    }
    
    // Return's the next smallest number
    int next() 
    {
        TreeNode *temp= s.top();
        s.pop();
        push_All(temp->right);
        return temp->val;
    }
    
    // Has next just return whether the stack is empty or not
    bool hasNext() 
    {
        return !s.empty();
    }
    
    private:
    // Push all the element's into the stack
    // First push all the left then it's left of right if exist's
    void push_All(TreeNode *node)
    {
        for(;node!=NULL;s.push(node),node= node->left);
    }
};

```
