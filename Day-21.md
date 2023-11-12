
## #Day21/100 09-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 39. Combination Sum <font color="Red"> -Unwatched </font>
#### Example 1:

Input: candidates = [2,3,6,7], target = 7\
Output: [[2,2,3],[7]]\
Explanation:
2 and 3 are candidates, and 2 + 2 + 3 = 7. Note that 2 can be used multiple times.
7 is a candidate, and 7 = 7.
These are the only two combinations.
#### Example 2:
Input: candidates = [2,3,5], target = 8\
Output: [[2,2,2,2],[2,3,3],[3,5]]
```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    void findCombi(int index,int target,vector<int>& candidates, vector<vector<int>>& ans,vector<int>& ds){
        if(index == candidates.size()){
            if(target == 0){
                ans.push_back(ds);
            }
            return;
        }

        // pick up the element
        if(candidates[index] <= target){
            ds.push_back(candidates[index]);
            findCombi(index,target - candidates[index],candidates,ans,ds);
            ds.pop_back();
        }

        findCombi(index + 1,target,candidates,ans,ds);
    }
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {
        vector<vector<int>> ans;
        vector<int> ds;
        findCombi(0,target,candidates,ans,ds);
        return ans;
    }
};
```
