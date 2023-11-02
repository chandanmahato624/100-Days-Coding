
## #Day14/100 02-1-23

I am starting a 100-day LeetCode coding challenge. This journey is about consistency, determination, and self-improvement. Each day, I'll embrace a new coding problem, unravel its mysteries, and emerge as a stronger coder. It's not just about challenges; it's about pushing boundaries and becoming the best version of myself. With every line of code I write, I'll be one step closer to my goals. Let's embark on this remarkable journey together, because the adventure is in the coding, and the rewards await those who persevere. ☺️
: smiley : 


### 290. Word Pattern <font color="Red"> -Unwatched </font>
#### Example 1:

Input: pattern = "abba", s = "dog cat cat dog"\
Output: true

#### Example 2:
Input: pattern = "abba", s = "dog cat cat fish"\
Output: false

```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    bool wordPattern(string pattern, string s) {
       unordered_map<char,string>mp;
        unordered_map<string,char>mp2;
        int j =0;
        int i =0;
        while( i<pattern.length() && j<s.length()){
         string str = "";

        while(j<s.length() && s[j]!=' '){
          str+=s[j];
          j++;
        }
        j++;
        if(mp.count(pattern[i]))
             if(mp[pattern[i]]!=str)return false;
         if(mp2.count(str))
          if(mp2[str]!=pattern[i])return false;
         //else 
             mp[pattern[i]]=str;
             mp2[str]=pattern[i];
         i++;
      }
      if(j<s.length())return false;
       if(i<pattern.length())return false;
      return true; 
    }
};
```

### 49. Group Anagrams <font color="Red"> -Unwatched </font>
#### Example 1:

Input: strs = ["eat","tea","tan","ate","nat","bat"]\
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]

#### Example 2:
Input: strs = [""]
Output: [[""]]
```bash
  Medium level coding questions
```
### Code

```javascript
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
             unordered_map<string, vector<string>> mp;
        
        for(auto x: strs){
            string word = x;
            sort(word.begin(), word.end());
            mp[word].push_back(x);
        }
        
        vector<vector<string>> ans;
        for(auto x: mp){
            ans.push_back(x.second);
        }
        return ans;
    }
};
```

### 219. Contains Duplicate II <font color="Red"> -Unwatched </font>

#### Example 1:

Input: nums = [1,2,3,1], k = 3\
Output: true

#### Example 2:
Input: nums = [1,0,1,1], k = 1\
Output: true
 
```bash
  Easy level coding questions
```


### Code

```javascript
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {
             unordered_map<int,int> mp;
        int n = nums.size();
        for(int i=0; i<n; i++)
        {
            if(mp.count(nums[i]))
            {
                if(abs(i-mp[nums[i]])<=k)
                    return true;
            }
            mp[nums[i]] = i;
        }
        return false;  
    }
};
```