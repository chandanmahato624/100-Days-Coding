
## #Day6/100 25-10-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 20. Valid Parentheses <font color="Red"> -Unwatched </font>

#### Example 1:

Input: s = "()"\
Output: true

#### Example 2:
Input: s = "()[]{}"\
Output: true

```bash
  Easy level coding questions
```


### JAVA-Code

```javascript
class Solution {
public:
    bool isValid(string s) {
        stack<char>ss;
        for(int i=0; i<s.length(); i++){
            if(s[i]=='[' || s[i]=='{' || s[i]=='('){
                ss.push(s[i]);
            }else{
                if(!ss.empty()){
                    if(ss.top()=='[' && s[i]==']' ||
                ss.top()=='{' && s[i]=='}' ||
                ss.top()=='(' && s[i]==')'){
                    ss.pop();
                }else{
                    return false;
                }
                }else{
                    return false;
                }
            }
        }
        if(ss.empty()){
            return true;
        }else{
            return false;
        }      
    }
};
```

### 141. Linked List Cycle  <font color="Red"> -Unwatched </font>
#### Example 1:

Input: head = [3,2,0,-4], pos = 1\
Output: true\
Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).

#### Example 2:
Input: head = [1,2], pos = 0\
Output: true\
Explanation: There is a cycle in the linked list, where the tail connects to the 0th node.
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
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    bool hasCycle(ListNode *head) {
     ListNode *slow = head, *fast = head;
        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
            if (slow == fast) return true;
        }
        
        return false;   
    }
};
```

### 21. Merge Two Sorted Lists <font color="Red"> -Unwatched </font>
$${\color{red}Red}$$

#### Example 1:

Input: list1 = [1,2,4], list2 = [1,3,4]\
Output: [1,1,2,3,4,4]

#### Example 2:
Input: list1 = [], list2 = []\
Output: []
 
```bash
  Easy level coding questions
```


### Code

```javascript
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        if(list1!=null && list2!=null){
        if(list1.val<list2.val){
            list1.next=mergeTwoLists(list1.next,list2);
            return list1;
            }
            else{
                list2.next=mergeTwoLists(list1,list2.next);
                return list2;
        }
        }
        if(list1==null)
            return list2;
        return list1;
    }
}
```