
## #Day12/100 29-10-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 201. Bitwise AND of Numbers Range 
#### Example 1:

Input: left = 5, right = 7\
Output: 4

#### Example 2:
Input: left = 0, right = 0\
Output: 0

```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    int rangeBitwiseAnd(int left, int right) {
      int count=0;
      while(left!=right){
          left=left>>1;
          right=right>>1;
          count++;
      } 
      return left<<count; 
    }
};
```

### 172. Factorial Trailing Zeroes
#### Example 1:

Input: n = 3\
Output: 0\
Explanation: 3! = 6, no trailing zero.

#### Example 2:
Input: n = 5\
Output: 1\
Explanation: 5! = 120, one trailing zero.
```bash
  Medium level coding questions
```
### Code

```javascript
class Solution {
public:
    int trailingZeroes(int n) {
        int count = 0;
        for(int i=5; i<=n; i=i*5){
            count = count + n/i;
        }
        return count;
    }
};
```

### 11. Container With Most Water <font color="Red"> -Unwatched </font>

#### Example 1:

Input: height = [1,8,6,2,5,4,8,3,7]\
Output: 49\
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.

#### Example 2:
Input: height = [1,1]\
Output: 1
 
```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    int maxArea(vector<int>& height) {
        int left = 0;
        int right = height.size() - 1;
        int maxArea = 0;

        while (left < right) {
            int currentArea = min(height[left], height[right]) * (right - left);
            maxArea = max(maxArea, currentArea);

            if (height[left] < height[right]) {
                left++;
            } else {
                right--;
            }
        }

        return maxArea;
    }
};
```