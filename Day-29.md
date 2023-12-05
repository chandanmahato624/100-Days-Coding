
## #Day29/100 03-12-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 1446. Consecutive Characters<font color="Red"> -NotClear </font>
#### Example 1:

Input: s = "leetcode"\
Output: 2\
Explanation: The substring "ee" is of length 2 with the character 'e' only.

#### Example 2:
Input: s = "abbcccddddeeeeedcba"\
Output: 5\
Explanation: The substring "eeeee" is of length 5 with the character 'e' only.
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    int maxPower(string s) {
        int maincnt = 1;
        int cnt = 1;
        for(int i=0; i<s.size()-1; i++){
            if(s[i]==s[i+1]){
                cnt++;
                if(maincnt<cnt){
                    maincnt=cnt;
                }
            }else{
                cnt=1;
            }
        }
        return maincnt;
    }
};
```
