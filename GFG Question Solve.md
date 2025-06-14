## ❓ 1. Question:
### Find the missing number from an array containing numbers from 1 to n with one number missing.

# Code
```java
class Solution {
    int missingNum(int arr[]) {
        int n = arr.length + 1;
        long sum = (long) n * (n + 1) / 2;
        long sumArr = 0;

        for (int j = 0; j < arr.length; j++) {
            sumArr += arr[j];
        }

        return (int) (sum - sumArr);
    }
}
```
---

## ❓ 2. Question:
### Given an array arr of integers, find all the elements that occur more than once in the array. If no element repeats, return an empty array.

#Code
```java
class Solution {
public:
vector<int> findDuplicates(vector<int>& arr) {
set<int> st;
vector<int> v;

        for(auto it = arr.begin(); it !=arr.end(); it++)
        {
           if (st.find(*it) != st.end())
           {
                v.push_back(*it);
            }
            else
            {
                st.insert(*it);
            }
        }
        return v;
}
};
```
---

