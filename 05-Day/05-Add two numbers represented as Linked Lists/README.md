5. https://leetcode.com/problems/add-two-numbers/

```cpp
Solution 1: Elementary Math

Intuition: 
Keep track of the carry using a variable and simulate digits-by-digits 
sum starting from the head of the list, which contains the least significant digit.

class Solution 
{
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) 
    {
        ListNode *dummy = new ListNode(); 
        ListNode *temp = dummy; 
        int carry = 0;
        
	while( (l1 != NULL || l2 != NULL) || carry) 
	{
            int sum = 0; 
            if(l1 != NULL) 
	    {
                sum += l1->val; 
                l1 = l1 -> next; 
            }
            
            if(l2 != NULL) 
	    {
                sum += l2 -> val; 
                l2 = l2 -> next; 
            }
            
            sum += carry; 
            carry = sum / 10; 
            ListNode *node = new ListNode(sum % 10); 
            temp -> next = node; 
            temp = temp -> next; 
        }
        return dummy -> next; 
    }
};
Time Complexity: O(max(m,n)). Assume that m and n represent the length of l1 and l2 respectively
the algorithm above iterates at most max(m,n) times.

Space Complexity: O(max(m,n)). The length of the new list is at most max(m,n)+1.

```
![image](https://user-images.githubusercontent.com/37560890/169434016-ee33f315-be6b-44b2-8959-ebb681f964bb.png)
