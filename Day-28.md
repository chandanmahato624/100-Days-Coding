
## #Day28/100 02-12-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 17. Letter Combinations of a Phone Number<font color="Red"> -NotClear </font>
#### Example 1:

Input: digits = "23"\
Output: ["ad","ae","af","bd","be","bf","cd","ce","cf"]

#### Example 2:
Input: digits = ""\
Output: []
```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
    private:
        void solve(string digits,string output, int index, vector<string> &ans, string mapping[]){
        if(index>=digits.length()){
            ans.push_back(output);
            return;
        }
        int number = digits[index]-'0';
        string valuee = mapping[number];

        for(int i=0; i<valuee.length(); i++){
            output.push_back(valuee[i]);
            solve(digits, output, index+1, ans, mapping);
            output.pop_back();
        }
    }
public:

    vector<string> letterCombinations(string digits) {
        vector<string> ans;
        if(digits.length()==0)
            return ans;

            string output = "";
            int index = 0;
            string mapping[10]={"","","abc","def","ghi","jkl","mno","pqrs","tuv",    "wxyz"};
            solve(digits, output, index, ans, mapping);
            return ans;
        
    }
};
```
