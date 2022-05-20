3. https://leetcode.com/problems/merge-two-sorted-lists/

```cpp

Solution 1: Using an externally linked list to store answers.

Approach :

Step 1: Create a new dummy node. It will have the value 0 and will point to NULL respectively. 
This will be the head of the new list. Another pointer to keep track of traversals in the new list.

Step 2:  Find the smallest among two nodes pointed by the head pointer of both input lists. Store that data in a new list created.

Step 3: Move the head pointer to the next node of the list whose value is stored in the new list.

Step 4: Repeat the above steps till any one of the head pointers stores NULL. 
Copy remaining nodes of the list whose head is not NULL in the new list.
```
![image](https://user-images.githubusercontent.com/37560890/169432883-443cf8ba-f5c6-4af9-9e8b-94e3a05f03e8.png)

```cpp
Solution 2: Inplace method without using extra space.

The idea to do it without extra space is to play around with the next pointers of nodes in
the two input lists and arrange them in a fashion such that all nodes are linked in increasing order of values.

Approach :

Step 1: Create two pointers, say l1 and l2. Compare the first node of both lists and find the small among the two.
Assign pointer l1 to the smaller value node.

Step 2: Create a pointer, say res, to l1. An iteration is basically iterating through 
both lists till the value pointed by l1 is less than or equal to the value pointed by l2.

Step 3: Start iteration. Create a variable, say, temp. 
It will keep track of the last node sorted list in an iteration. 

Step 4: Once an iteration is complete, link node pointed by temp to node pointed by l2. 
Swap l1 and l2.

Step 5: If any one of the pointers among l1 and l2 is NULL
then move the node pointed by temp to the next higher value node.

class Solution
{

public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) 
    {

        // when list1 is empty then 
        // our output will be same as list2
        if(l1 == NULL) return l2; 

        // when list2 is empty then our output 
        // will be same as list1
        if(l2 == NULL) return l1;

        // pointing l1 and l2 to smallest and greatest one
        if(l1->val > l2->val) std::swap(l1,l2);

        // act as head of resultant merged list
        ListNode* res = l1;

        while(l1 != NULL && l2 != NULL) 
	{
 
            ListNode* temp = NULL;

            while(l1 != NULL && l1->val <= l2->val) 
	    {

                temp = l1;//storing last sorted node  
                l1 = l1->next;
            }

            // link previous sorted node with 
            // next larger node in list2
            temp->next = l2;
            std::swap(l1,l2);
        }

        return res;
    }
};
Time Complexity :
We are still traversing both lists entirely in the worst-case scenario. 
So, it remains the same as O(N+M) where N is the number of nodes in list 1 and M is the number of nodes in list 2.

Space Complexity :
We are using the same lists just changing links to create our desired list. 
So no extra space is used. Hence, its space complexity is O(1). 


```
![image](https://user-images.githubusercontent.com/37560890/169433142-f0335ec5-dcc3-4f02-8dbe-554be2dcfc0f.png)

