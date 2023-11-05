
## #Day16/100 04-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 108. Convert Sorted Array to Binary Search Tree <font color="Red"> -Unwatched </font>
#### Example 1:

Input: nums = [-10,-3,0,5,9]\
Output: [0,-3,9,-10,null,5]\
Explanation: [0,-10,5,null,-3,null,9] is also accepted:

#### Example 2:
Input: nums = [1,3]\
Output: [3,1]\
Explanation: [1,null,3] and [3,1] are both height-balanced BSTs.
```bash
  Easy level coding questions
```


### Code

```javascript
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
class Solution {
public:
    TreeNode* sortedArrayToBST(vector<int>& nums) {
         if(nums.size()==0)return NULL;
         if(nums.size()==1) return new TreeNode(nums[0]);
         int middle = nums.size()/2;
         TreeNode* root = new TreeNode(nums[middle]);
         vector<int> leftsub(nums.begin(), nums.begin()+middle);
         vector<int> rightsub(nums.begin()+ middle+1, nums.end());
         root->left = sortedArrayToBST(leftsub);
         root->right = sortedArrayToBST(rightsub);
         return root;
    }
};
```

### 148. Sort List <font color="Red"> -Unwatched </font>
#### Example 1:

Input: head = [4,2,1,3]\
Output: [1,2,3,4]

#### Example 2:
Input: head = [-1,5,3,4,0]\
Output: [-1,0,3,4,5]
```bash
  Medium level coding questions
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
void mergesorting(ListNode** head){
        ListNode*first;
        ListNode*second;
        ListNode*current=*head;
        if(!current || !current->next)return;

        middle(current,&first,&second);

        mergesorting(&first);
        mergesorting(&second);

        *head=merge(first,second);
    }
     void middle(ListNode* current,ListNode** first,ListNode** second){
        ListNode* fast=current->next;
        ListNode* slow=current;

        while(fast!=NULL){
            fast=fast->next;
            if(fast!=NULL){
                fast=fast->next;
                slow=slow->next;
            }
        }
        *first=current;
        *second=slow->next;
        slow->next=NULL;
    }
    ListNode* merge(ListNode* first,ListNode* second){
        ListNode* final=NULL;

        if(!first)return second;
        if(!second)return first;

        if(first->val <= second->val){
            final=first;
            final->next=merge(first->next,second);
        }

        else{
            final=second;
            final->next=merge(first,second->next);
        }
        return final;
    }
    ListNode* sortList(ListNode* head) {
        mergesorting(&head);
        return head;
    }
};
```

### 61. Rotate List <font color="Red"> -Unwatched </font>

#### Example 1:

Input: head = [1,2,3,4,5], k = 2\
Output: [4,5,1,2,3]

#### Example 2:
Input: head = [0,1,2], k = 4\
Output: [2,0,1].
 
```bash
  Medium level coding questions
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
    ListNode* rotateRight(ListNode* head, int k) {
        if(head == NULL){
            return head;
        }
        ListNode* curr = head;
        int len = 1;

        while(curr->next != NULL){
            curr = curr->next;
            len++;
        }
        curr->next = head;
        k = k % len;
        k = len - k;

        while(k--){
            curr = curr -> next;
        }
        head = curr->next;
        curr->next = NULL;

        return head;
    }
};
```