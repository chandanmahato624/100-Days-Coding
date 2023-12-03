
## #Day27/100 01-12-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 78. Subsets<font color="Red"> -NotClear </font>
#### Example 1:

Input: nums = [1,2,3]\
Output: [[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]

#### Example 2:
Input: nums = [0]\
Output: [[],[0]]
```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:

vector<vector<int>> ans;

    void sub(vector<int> &nums, int i, vector<int>temp){
        if(i==nums.size()){
            ans.push_back(temp);
            return;
        }
        sub(nums, i+1, temp);
        temp.push_back(nums[i]);
        sub(nums, i+1, temp);
    }
    vector<vector<int>> subsets(vector<int>& nums) {
        vector<int>temp;
        sub(nums, 0, temp);
        return ans;
    }
};
```
