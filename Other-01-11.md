
## #Day13/100 01-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 169. Majority Element <font color="Red"> -Unwatched </font>
#### Example 1:

Input: nums = [3,2,3]\
Output: 3

#### Example 2:
Input: nums = [2,2,1,1,1,2,2]\
Output: 2
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        int n = nums.size();
        return nums[n/2];

    }
};
```

### 383. Ransom Note <font color="Red"> -Unwatched </font>
#### Example 1:

Input: ransomNote = "a", magazine = "b"\
Output: false

#### Example 2:
Input: ransomNote = "aa", magazine = "ab"\
Output: false
```bash
  Easy level coding questions
```
### Code

```javascript
class Solution {
public:
    bool canConstruct(string ransomNote, string magazine) {
       unordered_map<char, int> m;
       for(auto c: magazine){
          m[c]++;
       }
       for (auto c: ransomNote){
         if (m.find(c) == m.end() || m[c] <= 0){
           return false;
         }
         m[c]--;
       }
       return true;  
    }
};
```

### 69. Sqrt(x) <font color="Red"> -Unwatched </font>

#### Example 1:

Input: x = 4\
Output: 2\
Explanation: The square root of 4 is 2, so we return 2.

#### Example 2:
Input: x = 8\
Output: 2\
Explanation: The square root of 8 is 2.82842..., and since we round it down to the nearest integer, 2 is returned.
 
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    int mySqrt(int num) {
           int high=num,low=0;
        while(high>low){
            long int mid = low + ((long int)high - low + 1) / 2;
            if(mid<=sqrt(num))
                low = mid;
            else
                high = mid -1;
        }
        return low;
    }
};
```