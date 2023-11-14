
## #Day26/100 14-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 48. Rotate Image<font color="Red"> -Unwatched </font>
#### Example 1:

Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]\
Output: [[7,4,1],[8,5,2],[9,6,3]]

#### Example 2:
Input: matrix = [[5,1,9,11],[2,4,8,10],[13,3,6,7],[15,14,12,16]]\
Output: [[15,13,2,5],[14,3,4,1],[12,6,8,9],[16,7,10,11]]
```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
        int row = matrix.size();
        for(int i=0;i<row; i++){
            for(int j=0; j<=i;j++){
                swap(matrix[i][j], matrix[j][i]);
            }
        }
        for(int i=0;i<row;i++){
            reverse(matrix[i].begin(), matrix[i].end());
        }
    }
};
```
