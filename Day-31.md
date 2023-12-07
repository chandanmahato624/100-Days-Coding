
## #Day31/100 05-12-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 203. Remove Linked List Elements
#### Example 1:

Input: head = [1,2,6,3,4,5,6], val = 6\
Output: [1,2,3,4,5]

#### Example 2:
Input: head = [], val = 1\
Output: []
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
    ListNode* removeElements(ListNode* head, int val) {
        if(head==nullptr) return head;
        while(head!=nullptr && head->val==val){
            head = head->next;
        }
        
        ListNode* temp = head; 
        ListNode* prev = nullptr;
        while(temp!=nullptr){
            if(temp->val==val){
                prev->next=temp->next;
                temp = temp->next;
            }else{
                prev=temp;
                temp=temp->next;
            }
        }
        return head;
    }
};
```
