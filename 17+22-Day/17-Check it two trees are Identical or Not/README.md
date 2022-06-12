# [100. Same Tree (Easy)](https://leetcode.com/problems/same-tree/)

<p>Given two binary trees, write a function to check if they are the same or not.</p>

<p>Two binary trees are considered the same if they are structurally identical and the nodes have the same value.</p>

<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong>     1         1
          / \       / \
         2   3     2   3

        [1,2,3],   [1,2,3]

<strong>Output:</strong> true
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong>     1         1
          /           \
         2             2

        [1,2],     [1,null,2]

<strong>Output:</strong> false
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong>     1         1
          / \       / \
         2   1     1   2

        [1,2,1],   [1,1,2]

<strong>Output:</strong> false
</pre>


**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Depth-first Search](https://leetcode.com/tag/depth-first-search/)


## Video Notes


![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0180](https://user-images.githubusercontent.com/106215989/170277583-156f6865-f5c7-4ef5-ac1b-4e903faadcee.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0181](https://user-images.githubusercontent.com/106215989/170277592-ad2b70a0-ed83-41bb-bcc7-c07eba4a5881.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0182](https://user-images.githubusercontent.com/106215989/170277627-29d52d38-8072-4945-9b18-7e139cfce6f6.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0183](https://user-images.githubusercontent.com/106215989/170277658-fc2671fb-6f27-42db-8005-09b0def6994f.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0184](https://user-images.githubusercontent.com/106215989/170277662-561b551d-d619-42c3-b51f-e1aa57b9ecd8.jpg)
![1  Stiver video notes  1-53 -1-201_pages-to-jpg-0185](https://user-images.githubusercontent.com/106215989/170277668-a93d5ca4-062a-4f31-81f6-4043f6c1d484.jpg)


## Solution 1. Dfs

```cpp
// OJ: https://leetcode.com/problems/same-tree/
// Time: O(N)
// Space: O(H)

class Solution 
{
public:
    bool isSameTree(TreeNode* p, TreeNode* q) 
    {
        return (!p && !q) || (p && q && p->val == q->val && isSameTree(p->left, q->left) && isSameTree(p->right, q->right));
    }
};
```

## Solution 2. Dfs

```cpp
class Solution 
{
public:

    bool isSameTree(TreeNode* p, TreeNode* q) 
    {
        if(!p && !q) return true;
        
        if(p && q && p->val== q->val)
        {
            return (isSameTree(p->left, q->left) && isSameTree(p->right, q->right));
        }
        
        return false;
    }
};
```

## Solution 3. Bfs

```cpp

class Solution {
public:
	bool isSameTree(TreeNode* p, TreeNode* q) {

		//for iterative approach, we generally follow the 4 major steps:
		//1. Make a queue 
		//2. Push the current Node in the queue (starting from the root node)
		//3. Process the queue, while its not empty (by adding its left & right child)
		//4. Once the queue is empty, then alorithm has finished

		//Step 1
		queue<TreeNode*> qu;  

		//Step 2
		qu.push(p);
		qu.push(q);

		//step 3
		while(qu.size() != 0){
			TreeNode* n1 = qu.front();
			qu.pop();
			TreeNode* n2 = qu.front();
			qu.pop();

			//meet the question conditions
			if(n1 == NULL && n2 == NULL) continue;
			if(n1 == NULL || n2 == NULL) return false;
			if(n1->val != n2->val) return false;

			qu.push(n1->left);
			qu.push(n2->left);
			qu.push(n1->right);
			qu.push(n2->right);

		}
		
		//Step 4
		return true;
	}
};
```
