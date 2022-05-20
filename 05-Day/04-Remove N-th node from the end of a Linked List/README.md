4. https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```cpp
Solution 1: Naive Approach [Traverse 2 times]

Intuition: 
We can traverse through the Linked List while maintaining a count of nodes
let’s say in variable count , and then traversing for 
the 2nd time for (n – count) nodes to get to the nth node of the list.

```

```cpp
Solution 2: [Efficient] Two pointer method

Unlike the above approach, we don’t have to maintain the count value, 
we can find the nth node just by one traversal by using two pointer approach.

Intuition : 

What if we had to modify the same above approach to work in just one traversal?
Let’s see what all information we have here:

We have the flexibility of using two-pointers now.
We know, the n-th node from the end is the same as (total nodes – n)th node from start.
But, we are not allowed to calculate total nodes, as we can do only one traversal.
What if, one out of the two-pointers is at the nth node from start instead of end? Will it make anything easier for us?

Yes, with two pointers in hand out of which one at n-th node from start, 
we can just advance both of them till end simultaneously, once the faster reaches the end
the slower will stand at the n-th node from the end.

class Solution
{
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) 
    {
        ListNode * start = new ListNode();
        start -> next = head;
        ListNode* fast = start;
        ListNode* slow = start;     

        for(int i = 1; i <= n; ++i)
            fast = fast->next;
    
        while(fast->next != NULL)
        {
            fast = fast->next;
            slow = slow->next;
        }
        
        slow->next = slow->next->next;
        
        return start->next;
    }
};

Time Complexity: O(N)
Space Complexity: O(1)

```
![image](https://user-images.githubusercontent.com/37560890/169433721-40be6c40-9e3d-4424-81ea-ad3003c5fbc4.png)
