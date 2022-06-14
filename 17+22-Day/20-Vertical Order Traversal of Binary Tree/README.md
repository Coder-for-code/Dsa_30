# [987. Vertical Order Traversal of a Binary Tree (Medium)](https://leetcode.com/problems/vertical-order-traversal-of-a-binary-tree/)

<p>Given a binary tree, return the <em>vertical order</em> traversal of its nodes&nbsp;values.</p>

<p>For each node at position <code>(X, Y)</code>, its left and right children respectively&nbsp;will be at positions <code>(X-1, Y-1)</code> and <code>(X+1, Y-1)</code>.</p>

<p>Running a vertical line from <code>X = -infinity</code> to <code>X = +infinity</code>, whenever the vertical line touches some nodes, we report the values of the nodes in order from top to bottom (decreasing <code>Y</code> coordinates).</p>

<p>If two nodes have the same position, then the value of the node that is reported first is the value that is smaller.</p>

<p>Return an list&nbsp;of non-empty reports in order of <code>X</code> coordinate.&nbsp; Every report will have a list of values of nodes.</p>

<p>&nbsp;</p>

<p><strong>Example 1:</strong></p>

<p><img alt="" src="https://assets.leetcode.com/uploads/2019/01/31/1236_example_1.PNG" style="width: 201px; height: 186px;"></p>

<div>
<pre><strong>Input: </strong><span id="example-input-1-1">[3,9,20,null,null,15,7]</span>
<strong>Output: </strong><span id="example-output-1">[[9],[3,15],[20],[7]]</span>
<strong>Explanation: </strong>
Without loss of generality, we can assume the root node is at position (0, 0):
Then, the node with value 9 occurs at position (-1, -1);
The nodes with values 3 and 15 occur at positions (0, 0) and (0, -2);
The node with value 20 occurs at position (1, -1);
The node with value 7 occurs at position (2, -2).
</pre>

<div>
<p><strong>Example 2:</strong></p>

<p><strong><img alt="" src="https://assets.leetcode.com/uploads/2019/01/31/tree2.png" style="width: 236px; height: 150px;"></strong></p>

<pre><strong>Input: </strong><span id="example-input-2-1">[1,2,3,4,5,6,7]</span>
<strong>Output: </strong><span id="example-output-2">[[4],[2],[1,5,6],[3],[7]]</span>
<strong>Explanation: </strong>
The node with value 5 and the node with value 6 have the same position according to the given scheme.
However, in the report "[1,5,6]", the node value of 5 comes first since 5 is smaller than 6.
</pre>

<p>&nbsp;</p>
</div>

<p><strong>Note:</strong></p>

<ol>
	<li>The tree will have between <font face="monospace">1</font>&nbsp;and <code>1000</code> nodes.</li>
	<li>Each node's value will be between <code>0</code> and <code>1000</code>.</li>
</ol>
</div>

<div>
<div>&nbsp;</div>
</div>


**Related Topics**:  
[Hash Table](https://leetcode.com/tag/hash-table/), [Tree](https://leetcode.com/tag/tree/)

## Video Notes

![img277](https://user-images.githubusercontent.com/37560890/170310535-250828b4-d1c6-4d55-a44c-a96967ed4a09.jpg)
![img279](https://user-images.githubusercontent.com/37560890/170310548-cd54f825-56ba-4a81-8baa-392e411efd6e.jpg)
![img281](https://user-images.githubusercontent.com/37560890/170310555-90660479-c8d4-411f-87c4-efe920fbf0ad.jpg)
![img283](https://user-images.githubusercontent.com/37560890/170310560-3f76988b-808a-4dd3-8b96-2a8e7749aaf7.jpg)
![img285](https://user-images.githubusercontent.com/37560890/170310562-57c70643-906f-459e-9820-2e37e6bd22f0.jpg)
![img287](https://user-images.githubusercontent.com/37560890/170310565-5d89af1e-0052-4a97-968a-e43fcde29286.jpg)
![img289](https://user-images.githubusercontent.com/37560890/170310568-2777bed5-6ef8-4b70-9ceb-a297925b3454.jpg)
![img291](https://user-images.githubusercontent.com/37560890/170310574-08be7395-3d39-4944-8acd-d5916ebc1e21.jpg)
![img293](https://user-images.githubusercontent.com/37560890/170310577-1d4892d9-1c4c-41a1-93ee-20148b4c3b49.jpg)
![img295](https://user-images.githubusercontent.com/37560890/170310581-a3e98804-ebdb-45b3-b32f-a340cd19a5d4.jpg)
![img297](https://user-images.githubusercontent.com/37560890/170310586-083ad7d7-cda1-4b4b-b59f-265e6c69fc01.jpg)
![img299](https://user-images.githubusercontent.com/37560890/170310589-fefd53d8-4c57-4600-adc1-939f96655d64.jpg)
![img301](https://user-images.githubusercontent.com/37560890/170310595-71cbc940-0ed8-4812-a4b0-99180966a994.jpg)
![img303](https://user-images.githubusercontent.com/37560890/170310600-5462cb56-5c88-46fe-b295-6efb9cb09355.jpg)
![img305](https://user-images.githubusercontent.com/37560890/170310608-2fdd80f4-1fc9-4bf4-845d-51fad3c1b82f.jpg)
![img307](https://user-images.githubusercontent.com/37560890/170310614-a468e338-11b6-4cb8-a94d-14ff8a3e30b1.jpg)
![img309](https://user-images.githubusercontent.com/37560890/170310617-fadec928-b83b-4cc5-a2ec-3e6a612180d3.jpg)
![img311](https://user-images.githubusercontent.com/37560890/170310623-69ac34fd-f82d-4066-a9a0-51672c729cc0.jpg)
![img313](https://user-images.githubusercontent.com/37560890/170310625-5ddf9eff-65f8-4703-be23-8891fcae004a.jpg)
![img315](https://user-images.githubusercontent.com/37560890/170310631-91cdaaff-5b43-4239-959d-a73fe4963dfb.jpg)
![img317](https://user-images.githubusercontent.com/37560890/170310635-8e415b75-cd88-40a2-bc10-effd4a124a65.jpg)
![img319](https://user-images.githubusercontent.com/37560890/170310640-238ec7d4-5afb-45f2-b186-63f4d0f5117a.jpg)
![img321](https://user-images.githubusercontent.com/37560890/170310645-430d832a-c49b-4344-875e-c9fa75f883fa.jpg)
![img323](https://user-images.githubusercontent.com/37560890/170310651-af3f8e55-e3eb-4e83-8096-3c35ba02eb5a.jpg)
![img325](https://user-images.githubusercontent.com/37560890/170310654-7089ac3a-7d12-4b72-bd54-73853eb2adc2.jpg)
![img327](https://user-images.githubusercontent.com/37560890/170310662-5c366580-8928-4b6b-98b1-13171731006b.jpg)
![img329](https://user-images.githubusercontent.com/37560890/170310666-024ae29c-88bb-4443-8bb8-d0f84d6cdb9c.jpg)
![img331](https://user-images.githubusercontent.com/37560890/170310671-0aa0e9a8-1998-4b8d-845a-be79be4ad74e.jpg)


## Solution 2. Bfs

```cpp
class Solution 
{
public:
    vector<vector<int>> verticalTraversal(TreeNode* root) 
    {
        // Make a map<verticle,each level multiple nodes,Same value nodes>
        map<int,map<int,multiset<int>>> nodes;
        
        // For Bfs make a queue data strucutre
        // Q(node,verticle,level)
        queue<pair<TreeNode*, pair<int,int>>> q;
        
        // Push the first element i.e 1,0,0
        q.push({root,{0,0}});
        
        // Iterate till q is not empty
        while(!q.empty())
        {
            // Take the first node i.e (1,0,0)
            auto p= q.front();
            q.pop();
            
            // Get the node i.e 1
            TreeNode *node= p.first;
            
            // Get the verticle i.e 0
            int x= p.second.first;
            
            // Get the level i.e 0
            int y= p.second.second;
            
            // Push into the nodes i.e that is our final result
            nodes[x][y].insert(node->val);
            
            // If the node left exists then push into queue
            // x-1 because you are going left on number line
            if(node->left) q.push({node->left,{x-1, y+1} });
            
            // If the node right exists then push into queue
            // x+1 because you are going right on number line
            if(node->right) q.push({node->right , {x+1, y+1} });
                        
        }
        
        // For returning the final ans
        vector<vector<int>> ans;
        
        for(auto p: nodes)
        {
            vector<int> verticle_cols;
            
            for(auto q: p.second)
            {
                verticle_cols.insert(verticle_cols.end(),q.second.begin(),q.second.end());
            }
            ans.push_back(verticle_cols);
        }
        return ans;
    }
};
```

## Solution 2. Dfs


Use a `map<int, map<int, multiset<int>>> m` to store the values -- `m[node->x][node->y].insert(node->val)`. (Using `set` instead of `multiset` can also pass this problem. I guess LeetCode uses the node values as IDs and assumes the uniqueness of the values. I used `multiset` here to be safe.)

In this way, the values are sorted first in asending order of the `x` values, then in asending order of `y` values, then in asending order of node values.

Note that we shouldn't sort the values with the same X values all together, we should only sort them if they **have the same position**, i.e. when **both their `x` and `y` values are equal**.

```cpp
// OJ: https://leetcode.com/problems/vertical-order-traversal-of-a-binary-tree/
// Time: O(NlogN)
// Space: O(N)

class Solution 
{
    map<int, map<int, multiset<int>>> m;
    void dfs(TreeNode *root, int x, int y) 
    {
        if (!root) return;
        m[x][y].insert(root->val);
        dfs(root->left, x - 1, y + 1);
        dfs(root->right, x + 1, y + 1);
    }
public:
    vector<vector<int>> verticalTraversal(TreeNode* root) 
    {
        dfs(root, 0, 0);
        vector<vector<int>> ans;
        for (auto &[x, mm] : m) 
        {
            ans.emplace_back();
            for (auto &[y, vals] : mm) 
            {
                for (int n : vals) ans.back().push_back(n);
            }
        }
        return ans;
    }
};
```


