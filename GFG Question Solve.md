### ❓ 1. Question:
Find the missing number from an array containing numbers from 1 to n with one number missing.

---

### ✅ Solution (Java)

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


### ❓ Question:
You are given an array arr of positive integers. Your task is to find all the leaders in the array. An element is considered a leader if it is greater than or equal to all elements to its right. The rightmost element is always a leader.

Examples:

Input: arr = [16, 17, 4, 3, 5, 2]
Output: [17, 5, 2]
Explanation: Note that there is nothing greater on the right side of 17, 5 and, 2.
Input: arr = [10, 4, 2, 4, 1]
Output: [10, 4, 4, 1]
Explanation: Note that both of the 4s are in output, as to be a leader an equal element is also allowed on the right. side

## code

