### 🔎 Search Question on GFG and find more about it....

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

## ❓ 3. Question:

### You are given an array arr of positive integers. Your task is to find all the leaders in the array. An element is considered a leader if it is greater than or equal to all elements to its right. The rightmost element is always a leader.

#Code

```java
// This Is not a optimal solution its TC = 0(n^2)
class Solution {
    static ArrayList<Integer> leaders(int arr[]) {
        // code here
        ArrayList<Integer> al = new ArrayList<>();
        int n = arr.length;
        int i, j;
       for(i = 0; i < n; i++) {
    for(j = i+1; j < n; j++) {
        if(arr[i] < arr[j]) break;
    }
    if(j == n) al.add(arr[i]);
        }
           return al;
        }
}
```

```java
// This Is  a optimal solution its TC = 0(n)

class Solution {
    static ArrayList<Integer> leaders(int arr[]) {
        // code here
        ArrayList<Integer> al = new ArrayList<>();

      int n = arr.length;
    int lastElem = arr[n - 1]; // Last elem is always greater
    al.add(lastElem);

    // Starts from end 
    for (int i = n - 2; i >= 0; i--) {
        if (arr[i] >= lastElem) {
            lastElem = arr[i];  //update elem
            al.add(lastElem);
        }
    }

    Collections.reverse(al);
    return al;
    }
}

```
---



## ❓ 4. Question:

### Given an unsorted array arr of positive integers. One number a from the set [1, 2,....,n] is missing and one number b occurs twice in the array. Find numbers a and b.

Note: The test cases are generated such that there always exists one missing and one repeating number within the range [1,n].

#Code

```java
class Solution {
    // Function to find two elements in array
    ArrayList<Integer> findTwoElement(int arr[]) {
        // code here
        int n = arr.length;
        int [] app = new int [n+1];
        int rep = -1;
        int mis = -1;
        
        for(int i =0; i<n; i++){
            app[arr[i]]++;
        }
        for(int i =1; i<=n; i++){
            if(app[i] ==0){
                mis = i;
            }
            else if(app[i] == 2){
                rep =i;
            }
        }
        ArrayList<Integer> res = new ArrayList<>();
        res.add(rep);
        res.add(mis);
        return res;
    }
}

```
---
