
## #Day2/100 21-10-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 1. Rotate Array
Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

#### Example 1:

Input: nums = [1,2,3,4,5,6,7], k = 3\
Output: [5,6,7,1,2,3,4]\
Explanation:\
rotate 1 steps to the right: [7,1,2,3,4,5,6]\
rotate 2 steps to the right: [6,7,1,2,3,4,5]\
rotate 3 steps to the right: [5,6,7,1,2,3,4]

#### Example 2:
Input: nums = [-1,-100,3,99], k = 2\
Output: [3,99,-1,-100]\
Explanation: \
rotate 1 steps to the right: [99,-1,-100,3]\
rotate 2 steps to the right: [3,99,-1,-100]

```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        k%=nums.size();
        reverse(nums.begin(), nums.end());
        reverse(nums.begin(), nums.begin()+k);
        reverse(nums.begin()+k, nums.end());       
    }
};
```

### 2. Merge Sorted Array
#### Example 1:

Input: nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3\
Output: [1,2,2,3,5,6]\
Explanation: The arrays we are merging are [1,2,3] and [2,5,6].\
The result of the merge is [1,2,2,3,5,6] with the underlined elements coming from nums1.

#### Example 2:
Input: nums1 = [0], m = 0, nums2 = [1], n = 1\
Output: [1]\
Explanation: The arrays we are merging are [] and [1].\
The result of the merge is [1].\
Note that because m = 0, there are no elements in nums1. The 0 is only there to ensure the merge result can fit in nums1.

```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int k = (m+n)-1;
        int i=m-1;
        int j=n-1;
        while(i>=0 && j>=0){
            if(nums2[j]>nums1[i]){
                nums1[k]=nums2[j];
                j--;
                k--;
            }else{
                nums1[k]=nums1[i];
                i--;
                k--;
            }
        }
        while(i>=0){
            nums1[k--]=nums1[i--];
        }
        while(j>=0){
            nums1[k--]=nums2[j--];
        }        
    }
};
```
