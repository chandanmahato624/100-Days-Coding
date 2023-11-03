
## #Day15/100 03-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 74. Search a 2D Matrix <font color="Red"> -Unwatched </font>
#### Example 1:

Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3\
Output: true

#### Example 2:
Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13
Output: false
```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int rows = matrix.size(),
			cols = matrix[0].size(),
            row = 0, col = cols - 1;
			
        while (row < rows && col > -1) {
            int cur = matrix[row][col];
            if (cur == target) return true;
            if (target > cur) row++;
            else col--;
        }
        
        return false;
    }
};
```

### 33. Search in Rotated Sorted Array <font color="Red"> -Unwatched </font>
#### Example 1:

Input: nums = [4,5,6,7,0,1,2], target = 0\
Output: 4

#### Example 2:
Input: nums = [4,5,6,7,0,1,2], target = 3
Output: -1
```bash
  Medium level coding questions
```
### Code

```javascript
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int low = 0, high = nums.size() - 1;

        while (low <= high) {
            int mid = (low + high) / 2;

            if (nums[mid] == target) {
                return mid;
            }

            if (nums[low] <= nums[mid]) {
                if (nums[low] <= target && target < nums[mid]) {
                    high = mid - 1;
                } else {
                    low = mid + 1;
                }
            } else {
                if (nums[mid] < target && target <= nums[high]) {
                    low = mid + 1;
                } else {
                    high = mid - 1;
                }
            }
        }

        return -1;
    }
};
```

### 162. Find Peak Element <font color="Red"> -Unwatched </font>

#### Example 1:

Input: nums = [1,2,3,1]\
Output: 2\
Explanation: 3 is a peak element and your function should return the index number 2.

#### Example 2:
Input: nums = [1,2,1,3,5,6,4]\
Output: 5\
Explanation: Your function can return either index number 1 where the peak element is 2, or index number 5 where the peak element is 6.
 
```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    int findPeakElement(vector<int>& nums) {
        int n=nums.size();
        if(n==1) return 0;
        if(nums[0]>nums[1]) return 0;
        if(nums[n-1]>nums[n-2]) return n-1;
        int l=1,h=n-2;
        while(l<=h){
            int mid=l+(h-l)/2;
            if(nums[mid] >nums[mid+1] && nums[mid]>nums[mid-1]){
                return mid;
            }
            //increasing
            else if(nums[mid]>nums[mid-1]){
                l=mid+1;
            }
            //decreasing
            else if(nums[mid]>nums[mid+1]){
                h=mid-1;
            }
            //local minima
            else{
                l=mid+1;
            }
        }
        return -1;
    }
};
```