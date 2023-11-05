
## #Day17/100 05-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 6. Zigzag Conversion <font color="Red"> -Unwatched </font>
#### Example 1:

Input: s = "PAYPALISHIRING", numRows = 3\
Output: "PAHNAPLSIIGYIR"

#### Example 2:
Input: s = "PAYPALISHIRING", numRows = 4\
Output: "PINALSIGYAHRPI"\
Explanation:\
P     I    N\
A   L S  I G\
Y A   H R\
P     I
```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    string convert(string s, int numRows) {
        if(numRows <= 1) return s;

    vector<string>v(numRows, ""); 

    int j = 0, dir = -1;

    for(int i = 0; i < s.length(); i++)
    {

        if(j == numRows - 1 || j == 0) dir *= (-1); 
		 
        v[j] += s[i];

        if(dir == 1) j++;

        else j--;
    }

    string res;

    for(auto &it : v) res += it; 

    return res;

    }
};
```

### 55. Jump Game <font color="Red"> -Unwatched </font>
#### Example 1:

Input: nums = [2,3,1,1,4]\
Output: true\
Explanation: Jump 1 step from index 0 to 1, then 3 steps to the last index.

#### Example 2:
Input: nums = [3,2,1,0,4]\
Output: false\
Explanation: You will always arrive at index 3 no matter what. Its maximum jump length is 0, which makes it impossible to reach the last index.
```bash
  Medium level coding questions
```
### Code

```javascript
class Solution {
public:
    bool canJump(vector<int>& nums) {
         int n = nums.size();
    int maxReach = 0;
    for (int i = 0; i < n; i++) {
        if (i > maxReach) return false;
        maxReach = max(maxReach, i + nums[i]);
    }
    return true;
    }
};
```

### 274. H-Index <font color="Red"> -Unwatched </font>

#### Example 1:

Input: citations = [3,0,6,1,5]\
Output: 3\
Explanation: [3,0,6,1,5] means the researcher has 5 papers in total and each of them had received 3, 0, 6, 1, 5 citations respectively.
Since the researcher has 3 papers with at least 3 citations each and the remaining two with no more than 3 citations each, their h-index is 3.

#### Example 2:
Input: citations = [1,3,1]\
Output: 1
 
```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    int hIndex(vector<int>& citations) {
        sort(citations.rbegin(), citations.rend());
    int h = 0;
    while (h < citations.size() && citations[h] > h) {
        h++;
    }
    return h;
    }
};
```