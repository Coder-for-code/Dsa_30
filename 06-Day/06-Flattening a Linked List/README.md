6. https://practice.geeksforgeeks.org/problems/flattening-a-linked-list/1

```cpp
Approach:

Since each list, followed by the bottom pointer, are in sorted order. 
Our main aim is to make a single list in sorted order of all nodes. 
So, we can think of a merge algorithm of merge sort.

The process to flatten the given linked list is as follows:-

1. We will recurse until the head pointer moves null. 
2. The main motive is to merge each list from the last.
3. Merge each list chosen using the merge algorithm.
4. The steps are Create a dummy node. Point two pointers, i.e, temp and res on dummy node. 
5. res is to keep track of dummy node and temp pointer is to move ahead as we build the flatten list.
6. We iterate through the two chosen. Move head from any of the chosen list ahead whose current pointed node is smaller. 
7. Return the new flattened list found.


Node* mergeTwoLists(Node* a, Node* b) 
{
    
    Node *temp = new Node(0);
    Node *res = temp; 
    
    while(a != NULL && b != NULL) 
    {
        if(a->data < b->data) 
	{
            temp->bottom = a; 
            temp = temp->bottom; 
            a = a->bottom; 
        }
        else 
	{
            temp->bottom = b;
            temp = temp->bottom; 
            b = b->bottom; 
        }
    }
    
    if(a) temp->bottom = a; 
    else temp->bottom = b; 
    
    return res -> bottom; 
    
}
Node *flatten(Node *root)
{
   
        if (root == NULL || root->next == NULL) 
            return root; 
  
        // recur for list on right 
        root->next = flatten(root->next); 
  
        // now merge 
        root = mergeTwoLists(root, root->next); 
  
        // return the root 
        // it will be in turn merged with its left 
        return root; 
}
Time Complexity: O(N), where N is the total number of nodes present
Reason: We are visiting all the nodes present in the given list.

Space Complexity: O(1)
Reason: We are not creating new nodes or using any other data structure.
```
![image](https://user-images.githubusercontent.com/37560890/169630301-780a9c4d-936e-450e-bff9-17413080bc83.png)
