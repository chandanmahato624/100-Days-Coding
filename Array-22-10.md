
## #Day3/100 22-10-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 121. Best Time to Buy and Sell Stock

#### Example 1:

Input: prices = [7,1,5,3,6,4]\
Output: 5\
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

#### Example 2:
Input: prices = [7,6,4,3,1]\
Output: 0\
Explanation: In this case, no transactions are done and the max profit = 0.

```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int s = prices.size();
        int maxRight = prices[s-1];
        int maxProfit = 0;
        for(int i=s-2; i>=0; i--){
            maxRight = max(maxRight, prices[i]);
            maxProfit = max(maxProfit, maxRight - prices[i]);
        }
        return maxProfit;
        
    }
};
```

### 122. Best Time to Buy and Sell Stock II
#### Example 1:

Input: prices = [7,1,5,3,6,4]\
Output: 7\
Explanation: Buy on day 2 (price = 1) and sell on day 3 (price = 5), profit = 5-1 = 4.
Then buy on day 4 (price = 3) and sell on day 5 (price = 6), profit = 6-3 = 3.
Total profit is 4 + 3 = 7.

#### Example 2:
Input: prices = [1,2,3,4,5]\
Output: 4\
Explanation: Buy on day 1 (price = 1) and sell on day 5 (price = 5), profit = 5-1 = 4.
Total profit is 4.
```bash
  Medium level coding questions
```


### Code

```javascript
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int n = prices.size();
        int count = 0;
        for(int i=0; i<n-1; i++){
            if(prices[i+1]>prices[i]){
                count+=(prices[i+1]-prices[i]);
            }
        }
        return count;
    }
};
```

### 13. Roman to Integer
#### Example 1:

Input: s = "III"\
Output: 3\
Explanation: III = 3.

#### Example 2:
Input: s = "LVIII"\
Output: 58\
Explanation: L = 50, V= 5, III = 3.
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    int getValue(char ch){
        switch(ch){
            case 'I':return 1;
            case 'V':return 5;
            case 'X':return 10;
            case 'L':return 50;
            case 'C':return 100;
            case 'D':return 500;
            case 'M':return 1000;
            default:return 0;      
        }
    }
    int romanToInt(string s) {
        int n=s.size();
        int ans =0;
        for(int i=0; i<n; i++){
            if(i+1<n && getValue(s[i])<getValue(s[i+1])){
                ans+=-getValue(s[i]);
            }else{
                ans+=getValue(s[i]);
            }
        }
        return ans;
    }
};
```