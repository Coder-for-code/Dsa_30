1. https://leetcode.com/problems/reverse-linked-list/

```cpp
Solution: Reverse Linked List : Iterative

We will use three-pointers to traverse through the entire list and interchange links between nodes. 
One pointer to keep track of the current node in the list. 
The second one is to keep track of the previous node to the current node and change links.
Lastly, a pointer to keep track of nodes in front of current nodes.

class Solution 
{
public:

    ListNode* reverseList(ListNode* head) 
    {

       //step 1
        ListNode* prev_p = NULL;
        ListNode* current_p = head;
        ListNode* next_p;
       
       //step 2
        while(current_p) 
	{

            next_p = current_p->next;
            current_p->next = prev_p;
            
            prev_p = current_p;
            current_p = next_p;
        }

        head = prev_p; //step 3
        return head;
    }
};

Time Complexity: 
Since we are iterating only once through the list and achieving reversed list. 
Thus, the time complexity is O(N) where N is the number of nodes present in the list.

Space Complexity:
To perform given tasks, no external spaces are used except three-pointers.
So, space complexity is O(1).

```
![image](https://user-images.githubusercontent.com/37560890/169431653-dbfc3285-d41f-410d-8546-325e1c2b8a8a.png)

```cpp

Solution 2: Reverse a Linked List : Recursive

Intuition: 

This approach is very similar to the above 3 pointer approach. 
In the process of reversing, the base operation is manipulating the pointers of each node and at the end
the original head should be pointing towards NULL and the original last node should be ‘head’ of the reversed Linked List. 

class Solution 
{
public:
    ListNode* reverseList(ListNode* head) 
    {
        ListNode *newHead = NULL;
        
	while (head != NULL) 
	{
            ListNode *next = head->next;
            head->next = newHead;
            newHead = head;
            head = next;
        }
        return newHead;
    }
};
```
![image](https://user-images.githubusercontent.com/37560890/169431898-c6658057-f0fe-456b-b713-5501a50e113b.png)


```cpp
Solution 3: Using Recursion

We traverse to the end of the list recursively.
As we reach the end of the list, we make the end node the head. 
Then receive previous nodes and make them connected to the last one.
At last, we link the second node to the head and the first node to NULL. We return to our new head.

class Solution
{
public:

    ListNode* reverseList(ListNode* &head) 
    {

        if (head == NULL||head->next==NULL)
            return head;

        ListNode* nnode = reverseList(head->next);
        head->next->next = head;
        head->next = NULL;
        return nnode;
    }
};

Time Complexity:
We move to the end of the list and achieve our reversed list.
Thus, the time complexity is O(N) where N represents the number of nodes.

Space Complexity:
Apart from recursion using stack space, no external storage is used. Thus, space complexity is O(1).


```
