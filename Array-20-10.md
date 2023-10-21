
## #Day1/100 20.10.23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 1. Remove Duplicates from Sorted Array II

#### Example 1:

Input: nums = [1,1,1,2,2,3]\
Output: 5, nums = [1,1,2,2,3,_]\
Explanation: Your function should return k = 5, with the first five elements of nums being 1, 1, 2, 2 and 3 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).

#### Example 2:
Input: nums = [0,0,1,1,1,1,2,3,3]\
Output: 7, nums = [0,0,1,1,2,3,3,_,_]\
Explanation: Your function should return k = 7, with the first seven elements of nums being 0, 0, 1, 1, 2, 3 and 3 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).

```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int i=0;
        for(auto e:nums){
            if(i==0 || i==1 || nums[i-2]!=e){
                nums[i]=e;
                i++;
            }
        }
        return i;
        
    }
};
```

### 2. Remove Element
#### Example 1:

Input: nums = [3,2,2,3], val = 3\
Output: 2, nums = [2,2,_,_]\
Explanation: Your function should return k = 2, with the first two elements of nums being 2.
It does not matter what you leave beyond the returned k (hence they are underscores).

#### Example 2:
Input: nums = [0,1,2,2,3,0,4,2], val = 2\
Output: 5, nums = [0,1,4,0,3,_,_,_]\
Explanation: Your function should return k = 5, with the first five elements of nums containing 0, 0, 1, 3, and 4.
Note that the five elements can be returned in any order.
It does not matter what you leave beyond the returned k (hence they are underscores).

```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int k=0;
        for(auto e:nums){
            if(e!=val){
                nums[k]=e;
                k++;
            }
        }
        return k;
        
    }
};
```

