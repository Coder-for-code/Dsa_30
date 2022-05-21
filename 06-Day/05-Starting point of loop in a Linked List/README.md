5. https://leetcode.com/problems/linked-list-cycle-ii/

```cpp
Solution 1: Brute Force

Approach:

We can store nodes in a hash table so that, if a loop exists

the head will encounter the same node again. 
This node will be present in the table and hence, we can detect the loop. Steps are:-

1. Iterate the given list.
2. For each node visited by head pointer, check if node is present in the hash table.
3. If yes, loop detected
4. If not, insert node in the hash table and move the head pointer ahead.
5. If head reaches null, then the given list does not have a cycle in it.


class node
{
    public:
        int num;
        node* next;
        node(int val) 
	{
            num = val;
            next = NULL;
        }
};

void insertNode(node* &head,int val) 
{
    node* newNode = new node(val);
    if(head == NULL) 
    {
        head = newNode;
        return;
    }
    node* temp = head;
    while(temp->next != NULL) temp = temp->next;
    temp->next = newNode;
    return;
}

void createCycle(node* &head,int pos)
{
    node* ptr = head;
    node* temp = head;
    int cnt = 0;
    
    while(temp->next != NULL) 
    {
        if(cnt != pos) 
	{
            ++cnt;
            ptr = ptr->next;
        } 
        temp = temp->next;
    }
    temp->next = ptr;
}

//process as per mentioned in solution
node* detectCycle(node* head) 
{
    unordered_set<node*> st;
    while(head != NULL)
    {
        if(st.find(head) != st.end()) return head;
        st.insert(head);
        head = head->next;
    }
    return NULL;
}

int main() 
{
    node* head = NULL;
    
    insertNode(head,1);
    insertNode(head,2);
    insertNode(head,3);
    insertNode(head,4);
    insertNode(head,3);
    insertNode(head,6);
    insertNode(head,10);
    
    createCycle(head,2);
    
    node* nodeRecieve = detectCycle(head);
    if(nodeRecieve == NULL) cout<<"No cycle";
    else 
    {
        node* temp = head;
        int pos = 0;
        while(temp!=nodeRecieve) 
	{
            ++pos;
            temp = temp->next;
        }
        cout<<"Tail connects at pos "<<pos<<endl;
    }
    
    return 0;
}

Time Complexity: O(N) Reason: Iterating the entire list once.

Space Complexity: O(N) Reason: We store all nodes in a hash table.
```
![image](https://user-images.githubusercontent.com/37560890/169630059-44d1c3ad-3cfc-4cb5-a127-89987cf4713d.png)


```cpp
Solution 2: Slow and Fast Pointer Method

Approach:

The following steps are required:

1. Initially take two pointers, fast and slow. 
2. Fast pointer takes two steps ahead while slow pointer will take single step ahead for each iteration.
3. We know that if a cycle exists, fast and slow pointers will collide.
4. If cycle does not exists, fast pointer will move to NULL
5. Else, when both slow and fast pointer collides, it detects a cycle exists.
6. Take another pointer, say entry. Point to the very first of the linked list.
7. Move the slow and the entry pointer ahead by single steps until they collide. 
8. Once they collide we get the starting node of the linked list.

But why use another pointer, entry?

Let’s say a slow pointer covers the L2 distance from the starting node of the cycle
until it collides with a fast pointer. 

L1 be the distance traveled by the entry pointer to the starting node of the cycle. 

So, in total, the slow pointer covers the L1+L2 distance. We know that a fast pointer covers some 
steps more than a slow pointer.

Therefore, we can say that a fast pointer will surely cover the L1+L2 distance. 

Plus, a fast pointer will cover more steps which will accumulate to nC length where cC is 
the length of the cycle and n is the number of turns. Thus, the fast pointer covers the total length of L1+L2+nC. 

We know that the slow pointer travels twice the fast pointer.

So this makes equation to
2(L1+L2) = L1+L2+nC. This makes equation to
L1+L2 = nC. Moving L2 to the right side
L1 = nC-L2 and this shows why the entry pointer and the slow pointer would collide.


#include<bits/stdc++.h>
using namespace std;

class node
{
    public:
        int num;
        node* next;
        node(int val) 
	{
            num = val;
            next = NULL;
        }
};

void insertNode(node* &head,int val) 
{
    node* newNode = new node(val);
    if(head == NULL) 
    {
        head = newNode;
        return;
    }
    node* temp = head;
    while(temp->next != NULL) temp = temp->next;
    
    temp->next = newNode;
    return;
}

void createCycle(node* &head,int pos) 
{
    node* ptr = head;
    node* temp = head;
    int cnt = 0;
    while(temp->next != NULL) 
    {
        if(cnt != pos) 
	{
            ++cnt;
            ptr = ptr->next;
        } 
        temp = temp->next;
    }
    temp->next = ptr;
}
//process as per mentioned in solution

node* detectCycle(node* head) 
{
    if(head == NULL||head->next == NULL) return NULL;
        
    node* fast = head;
    node* slow = head;
    node* entry = head;
        
    while(fast->next != NULL&&fast->next->next != NULL) 
    {
        slow = slow->next;
        fast = fast->next->next;
            
        if(slow == fast) 
	{
            while(slow != entry) 
	    {
                slow = slow->next;
                entry = entry->next;
            }
            return slow;
        }
    }
    return NULL;
}

int main()
{
    node* head = NULL;
    
    insertNode(head,1);
    insertNode(head,2);
    insertNode(head,3);
    insertNode(head,4);
    insertNode(head,3);
    insertNode(head,6);
    insertNode(head,10);
    
    createCycle(head,2);
    
    node* nodeRecieve = detectCycle(head);
    if(nodeRecieve == NULL) cout<<"No cycle";
    else
    {
        node* temp = head;
        int pos = 0;
        
	while(temp!=nodeRecieve) 
	{
            ++pos;
            temp = temp->next;
        }
        cout<<"Tail connects at pos "<<pos<<endl;
    }
    
    return 0;
}

Time Complexity: O(N) Reason: We can take overall iterations club it to O(N)

Space Complexity: O(1) Reason: No extra data structure is used.

```

![image](https://user-images.githubusercontent.com/37560890/169630153-8e1a04a1-e3d8-4c93-9b95-102785f93649.png)

