
## #Day25/100 13-11-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 2469. Convert the Temperature
#### Example 1:

Input: celsius = 122.11\
Output: [395.26000,251.79800]\
Explanation: Temperature at 122.11 Celsius converted in Kelvin is 395.26 and converted in Fahrenheit is 251.798.

#### Example 2:
Input: celsius = 36.50\
Output: [309.65000,97.70000]\
Explanation: Temperature at 36.50 Celsius converted in Kelvin is 309.65 and converted in Fahrenheit is 97.70.
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    vector<double> convertTemperature(double celsius) {
        vector<double>v1;
        v1.push_back(celsius+273.15);
        v1.push_back(celsius*1.80+32.00);
        return v1;
    }
};
```
