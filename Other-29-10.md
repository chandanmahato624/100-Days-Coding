
## #Day1/100 29-10-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 202. Happy Number <font color="Red"> -Unwatched </font>

#### Example 1:

Input: n = 19\
Output: true\
Explanation:\
12 + 92 = 82\
82 + 22 = 68\
62 + 82 = 100\
12 + 02 + 02 = 1

#### Example 2:
Input: n = 2\
Output: false

```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
    public boolean isHappy(int n) {
         int sum = n;//GIVE VALUE TO SUM
        while (sum != 1 && sum!=4 ) {
            int temp = sum;//THEN TEMP
            sum = 0;
            while (temp != 0 ) {
                int digit = temp % 10;
                sum += digit * digit;//ADDING VALUES
                temp =temp/ 10;
            }
        }
        return sum == 1;
    }
}
```

### 112. Path Sum <font color="Red"> -Unwatched </font>
#### Example 1:

Input: root = [5,4,8,11,null,13,4,7,2,null,null,null,1], targetSum = 22\
Output: true\
Explanation: The root-to-leaf path with the target sum is shown.

#### Example 2:
Input: root = [1,2,3], targetSum = 5\
Output: false\
Explanation: There two root-to-leaf paths in the tree:\
(1 --> 2): The sum is 3.\
(1 --> 3): The sum is 4.\
There is no root-to-leaf path with sum = 5.
```bash
  Easy level coding questions
```
### JAVA-Code

```javascript
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public boolean hasPathSum(TreeNode root, int targetSum) {
        if (root == null) {
            return false;
        }
        
        // Check if the current node is a leaf node and its value matches the targetSum
        if (root.left == null && root.right == null && root.val == targetSum) {
            return true;
        }
        
        // Recursively check the left and right subtrees with updated targetSum
        return hasPathSum(root.left, targetSum - root.val) || hasPathSum(root.right, targetSum - root.val);
    }
}
```

### 35. Search Insert Position <font color="Red"> -Unwatched </font>

#### Example 1:

Input: nums = [1,3,5,6], target = 5\
Output: 2

#### Example 2:
Input: nums = [1,3,5,6], target = 2\
Output: 1\
 
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
    public int searchInsert(int[] nums, int target) {
        int start = 0;
        int end = nums.length-1;

        while (start <= end) {
            int mid = start + (end-start)/2;
            if (nums[mid] == target) return mid;
            else if (nums[mid] > target) end = mid-1;
            else start = mid+1;
        }

        return start;
    }
}
```