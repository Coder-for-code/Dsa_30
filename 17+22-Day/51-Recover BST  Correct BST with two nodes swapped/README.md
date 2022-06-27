# [99. Recover Binary Search Tree (Hard)](https://leetcode.com/problems/recover-binary-search-tree/)

<p>Two elements of a binary search tree (BST) are swapped by mistake.</p>

<p>Recover the tree without changing its structure.</p>

<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> [1,3,null,null,2]

&nbsp;  1
&nbsp; /
&nbsp;3
&nbsp; \
&nbsp;  2

<strong>Output:</strong> [3,1,null,null,2]

&nbsp;  3
&nbsp; /
&nbsp;1
&nbsp; \
&nbsp;  2
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> [3,1,4,null,null,2]

  3
 / \
1   4
&nbsp;  /
&nbsp; 2

<strong>Output:</strong> [2,1,4,null,null,3]

  2
 / \
1   4
&nbsp;  /
 &nbsp;3
</pre>

<p><strong>Follow up:</strong></p>

<ul>
	<li>A solution using O(<em>n</em>) space is pretty straight forward.</li>
	<li>Could you devise a constant space solution?</li>
</ul>


**Related Topics**:  
[Tree](https://leetcode.com/tag/tree/), [Depth-first Search](https://leetcode.com/tag/depth-first-search/)


## Video Notes

![img200](https://user-images.githubusercontent.com/37560890/170563650-ba8450ff-6412-4945-8c8e-03518c446dee.jpg)
![img202](https://user-images.githubusercontent.com/37560890/170563656-833dba12-66de-4a03-a221-51941ff2effd.jpg)
![img204](https://user-images.githubusercontent.com/37560890/170563660-9e3d26c5-6bbb-4a3b-a5d6-37657b806717.jpg)
![img206](https://user-images.githubusercontent.com/37560890/170563662-381f01bc-2c12-47c2-9bea-2b1a5d7d0cd8.jpg)
![img208](https://user-images.githubusercontent.com/37560890/170563665-beaab235-a6ac-4b23-b572-e859ceec4f67.jpg)
![img210](https://user-images.githubusercontent.com/37560890/170563667-45a1fdb9-9fd1-4a59-a491-73a003560af5.jpg)
![img212](https://user-images.githubusercontent.com/37560890/170563672-02c63aaf-7cf5-483c-9f0d-c01beeb0c3bd.jpg)
![img214](https://user-images.githubusercontent.com/37560890/170563677-7b66c353-c3f6-4d52-8e82-7ddc7bda73a7.jpg)
![img216](https://user-images.githubusercontent.com/37560890/170563679-37559b2f-b3f6-4af6-96a2-35629d0207b8.jpg)
![img218](https://user-images.githubusercontent.com/37560890/170563680-00a96aeb-1e17-443d-bc8e-ebc5ecb5fa7c.jpg)
![img220](https://user-images.githubusercontent.com/37560890/170563681-906790ff-c449-4902-beae-4e473691ce83.jpg)
![img222](https://user-images.githubusercontent.com/37560890/170563683-64f58202-c5b3-4c7d-8524-bd6882338425.jpg)
![img224](https://user-images.githubusercontent.com/37560890/170563685-c3797393-c663-4c2b-8572-5d5b037d7453.jpg)
![img226](https://user-images.githubusercontent.com/37560890/170563686-b86e0fce-2305-463f-85f7-654be697fb67.jpg)
![img228](https://user-images.githubusercontent.com/37560890/170563687-5b715d15-38f5-47d4-b4e0-045e5138892f.jpg)
![img230](https://user-images.githubusercontent.com/37560890/170563688-b9149e8b-9802-481b-9574-e258c3ef8781.jpg)
![img232](https://user-images.githubusercontent.com/37560890/170563689-af1e7f22-dde3-4fe4-b502-5e7e26710909.jpg)
![img234](https://user-images.githubusercontent.com/37560890/170563690-4a85cacc-0eb0-4bbe-94a1-0e6a4b25cd95.jpg)
![img236](https://user-images.githubusercontent.com/37560890/170563693-555945d0-475e-4bc5-a2db-6a6f322d6c4b.jpg)
![img238](https://user-images.githubusercontent.com/37560890/170563699-010cdef5-2c1a-48ad-a7bd-366d61d82aa2.jpg)
![img240](https://user-images.githubusercontent.com/37560890/170563700-1147eadc-c29b-4bc6-b9fd-b8d4b1416ec9.jpg)
![img242](https://user-images.githubusercontent.com/37560890/170563702-bae37b2e-bd91-44bd-8002-528887dc0a5c.jpg)
![img244](https://user-images.githubusercontent.com/37560890/170563704-2703bd23-591f-4e7e-b2cd-87fb32597829.jpg)
![img246](https://user-images.githubusercontent.com/37560890/170563706-6785ded1-7f05-4d32-9407-873b703abb43.jpg)
![img248](https://user-images.githubusercontent.com/37560890/170563708-1b32666c-8c99-425d-b47b-7b18a22012fd.jpg)
![img250](https://user-images.githubusercontent.com/37560890/170563710-8b9e1554-39f7-4066-884f-d00ff4d3e852.jpg)
![img252](https://user-images.githubusercontent.com/37560890/170563712-4536d0da-4fff-42b5-82d0-64593737c5f1.jpg)
![img254](https://user-images.githubusercontent.com/37560890/170563715-aa75865a-3f49-4708-8429-d08c684e6864.jpg)
![img256](https://user-images.githubusercontent.com/37560890/170563717-3d8e7c85-38cd-44bf-9898-82780189bd2d.jpg)
![image](https://user-images.githubusercontent.com/37560890/175852831-9b2f13f1-16af-41dd-aab5-8ca7dc27f42b.png)


## Solution 1. DFS


```cpp
// OJ: https://leetcode.com/problems/recover-binary-search-tree/
// Time: O(N)
// Space: O(H)

/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution 
{
private: 
    TreeNode* first;
    TreeNode* prev;
    TreeNode* middle;
    TreeNode* last; 
private: 
    void inorder(TreeNode* root) 
    {
        if(root == NULL) return; 
        
        inorder(root->left);
        
        if (prev != NULL && (root->val < prev->val))
        {
           
            // If this is first violation, mark these two nodes as
            // 'first' and 'middle'
            if ( first == NULL )
            {
                first = prev;
                middle = root;
            }
 
            // If this is second violation, mark this node as last
            else
                last = root;
        }
 
        // Mark this node as previous
        prev = root;
        inorder(root->right); 
    }
public:
    void recoverTree(TreeNode* root) 
    {
        first = middle = last = NULL; 
        prev = new TreeNode(INT_MIN); 
        inorder(root);
        if(first && last) swap(first->val, last->val); 
        else if(first && middle) swap(first->val, middle->val); 
    }
};

```
