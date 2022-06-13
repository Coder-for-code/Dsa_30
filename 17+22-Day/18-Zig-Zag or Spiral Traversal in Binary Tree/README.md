# [103. Binary Tree Zigzag Level Order Traversal (Medium)](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/)

<p>Given a binary tree, return the <i>zigzag level order</i> traversal of its nodes' values. (ie, from left to right, then right to left for the next level and alternate between).</p>

<p>
For example:<br>
Given binary tree <code>[3,9,20,null,null,15,7]</code>,<br>
</p><pre>    3
   / \
  9  20
    /  \
   15   7
</pre>
<p></p>
<p>
return its zigzag level order traversal as:<br>
</p><pre>[
  [3],
  [20,9],
  [15,7]
]
</pre>
<p></p>

**Related Topics**:  
[Stack](https://leetcode.com/tag/stack/), [Tree](https://leetcode.com/tag/tree/), [Breadth-first Search](https://leetcode.com/tag/breadth-first-search/)

**Similar Questions**:
* [Binary Tree Level Order Traversal (Medium)](https://leetcode.com/problems/binary-tree-level-order-traversal/)



## Video Notes

![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0186](https://user-images.githubusercontent.com/106215989/170277883-e5152c59-d41f-4acb-8ec6-63b6b99d35d4.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0187](https://user-images.githubusercontent.com/106215989/170277892-79abf567-f701-48de-a6be-ddaddd8382ec.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0188](https://user-images.githubusercontent.com/106215989/170277894-7e8f9fe0-c176-4652-a3d0-ba6b916eaf65.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0189](https://user-images.githubusercontent.com/106215989/170277896-d2d00f88-06f2-4756-9f4f-11247eed974c.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0190](https://user-images.githubusercontent.com/106215989/170277901-81dec63f-d5c7-4b6d-86e6-269f4b74ee15.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0191](https://user-images.githubusercontent.com/106215989/170277903-917c05cb-68f5-4aaf-97f8-6efe1e9fe15e.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0192](https://user-images.githubusercontent.com/106215989/170277907-1fc4aedc-a9fd-46fc-824b-59cee3d76e43.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0193](https://user-images.githubusercontent.com/106215989/170277910-4d3e7bf4-eef6-4067-9723-15391f892839.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0194](https://user-images.githubusercontent.com/106215989/170277914-3f482a73-2428-48d3-b049-0df17e610dd4.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0195](https://user-images.githubusercontent.com/106215989/170277917-69144d98-1b69-4e03-8425-a51670622f7e.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0196](https://user-images.githubusercontent.com/106215989/170277921-d6132896-3873-481f-8da2-76ec8faae124.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0197](https://user-images.githubusercontent.com/106215989/170277925-e41a5de9-9ecd-42fa-957a-365dffef27fc.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0198](https://user-images.githubusercontent.com/106215989/170277930-63bdbacb-6b7d-42e8-a000-68f1fb92564c.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0199](https://user-images.githubusercontent.com/106215989/170277938-33b31a31-eba4-429d-b5c7-78ef2bf731a5.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0200](https://user-images.githubusercontent.com/106215989/170277942-b6f6869c-c2db-4fe8-ad90-71669dbfcf1c.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0201](https://user-images.githubusercontent.com/106215989/170277949-fef4c93c-37c0-4f67-908f-71b94f06017d.jpg)


## Solution 1. Bfs

```cpp
// Time: O(N)
// Space: O(N)


class Solution 
{
public:
    vector<vector<int>> zigzagLevelOrder(TreeNode* root) 
    {
        // Make a result vector
        vector<vector<int>> result;
        
        // If not root then return the result
        if(!root) return result;
        
        // Make a queue
        queue<TreeNode *> q;
        q.push(root);
        
        // Make a boolean variable
        bool left_to_right=true;
        
        // Iterate till queue not empty
        // This processing is for the particular level
        while(!q.empty())
        {
            int size= q.size();
            
            // Temp vector for storing the elements of that row
            vector<int> row(size);
            
            // Process the queue
            for(int i=0;i<size;i++)
            {
                TreeNode *node= q.front();
                q.pop();
                
                // Smart logic to put the element in front or back
                int index=(left_to_right)?i: (size-1-i);
                
                // Insert into temp vector for particular level
                row[index]= node->val;
                
                // Check for it's left child
                if(node->left) q.push(node->left);
                
                // Check for the right child
                if(node->right) q.push(node->right);
                
            }
            
            // After this level 
            left_to_right= !left_to_right;
            result.push_back(row);
        }
        return result;
        
    }
};
```

## Solution 2. Bfs

```cpp
// OJ: https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal
// Time: O(N)
// Space: O(N)

class Solution 
{
public:
    vector<vector<int>> zigzagLevelOrder(TreeNode* root) 
    {
        if (!root) return {};
        queue<TreeNode*> q;
        q.push(root);
        bool l2r = true;
        vector<vector<int>> ans;
    
        while (q.size()) 
        {
            int cnt = q.size();
            vector<int> lv;
            while (cnt--) 
            {
                root = q.front();
                q.pop();
                lv.push_back(root->val);
                if (root->left) q.push(root->left);
                if (root->right) q.push(root->right);
            }
            
            if (!l2r) reverse(begin(lv), end(lv));
            ans.push_back(lv);
            l2r = !l2r;
        }
        return ans;
    }
};
```

## Solution 3. Bfs

```cpp
// OJ: https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/
// Time: O(N)
// Space: O(N)

class Solution 
{

public:
    vector<vector<int>> zigzagLevelOrder(TreeNode* root) 
    {
        if (!root) return {};
        vector<vector<int>> ans;
        deque<TreeNode*> q;
        q.push_front(root);
        bool l2r = true;
    
        while (q.size()) 
        {
            int cnt = q.size();
            ans.emplace_back();
            while (cnt--) 
            {
                if (l2r) 
                {
                    root = q.front();
                    q.pop_front();
                }
                else 
                {
                    root = q.back();
                    q.pop_back();
                }
                ans.back().push_back(root->val);
                
                if (l2r) 
                {
                    if (root->left) q.push_back(root->left);
                    if (root->right) q.push_back(root->right);
                }
                else 
                {
                    if (root->right) q.push_front(root->right);
                    if (root->left) q.push_front(root->left);
                }
            }
            l2r = !l2r;
        }
        return ans;
    }
};
```

