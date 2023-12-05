
## #Day30/100 04-12-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 876. Middle of the Linked List<font color="Red"> -NotClear </font>
#### Example 1:

Input: head = [1,2,3,4,5]\
Output: [3,4,5]\
Explanation: The middle node of the list is node 3.

#### Example 2:
Input: head = [1,2,3,4,5,6]
Output: [4,5,6]
Explanation: Since the list has two middle nodes with values 3 and 4, we return the second one
```bash
  Easy level coding questions
```


### Code

```javascript
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    int countNode(ListNode* head)
    {
        int count = 0;
        for (ListNode* tmp = head; tmp; tmp = tmp->next) count++;
        return count;
    }
    ListNode* middleNode(ListNode* head) {
        int amount = countNode(head);
        int position = amount / 2 + 1;
        int count = 0;
        for (ListNode* tmp = head; tmp; tmp = tmp->next) 
        {
            count++;
            if (count == position) return tmp;
        }
        return head;
    }
};
```
