## Only 10 Questions Here 
---
---
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
⚠️
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

## ❓ 5. Question:

### Given an array arr[]. Rotate the array to the left (counter-clockwise direction) by d steps, where d is a positive integer. Do the mentioned change in the array in place.

Note: Consider the array as circular.
#Code

```java
// this is not a optimal solution...
class Solution {
    // Function to rotate an array by d elements in counter-clockwise direction.
    static void rotateArr(int arr[], int d) {
       int n= arr.length;
       d = d%n;
      int[] temp = new int[d];
        for(int i =0; i<d; i++){
            temp[i] = arr[i];
        }
        for(int i =d; i<n; i++){
            arr[i-d] = arr[i];
        }
        for(int i =n-d; i<n; i++){
            arr[i] = temp[i-(n-d)];
        }
    }
}
```
---

 ### ⏭️⏭️ Given an array arr[]. Rotate the array to the right by d steps, where d is a positive integer. 

#Code

```java
public static void RightRotate(int arr[], int n, int k) {
        k = k % n;
        int[] temp = new int[k];
        // Copy from end of original array
        for (int i = 0; i < k; i++) {
            temp[i] = arr[n - k + i];
        }
        // Step 2: Shift remaining elements to the right
        for (int i = n - 1; i >= k; i--) {
            arr[i] = arr[i - k];
        }
        // Step 3: Copy temp elements to the front
        for (int i = 0; i < k; i++) {
            arr[i] = temp[i];
        }
    }
}
```
---

## ❓ 6. Question:

### Given a sorted array arr and an integer k, find the position(0-based indexing) at which k is present in the array using binary search.

Note: If multiple occurrences are there, please return the smallest index.
#Code

```java
// Arrays.binarySearch() does not guarantee returning the first index of a duplicate element.
import java.util.Arrays;
class Solution {
    public int binarysearch(int[] arr, int k) {
        int res =  Arrays.binarySearch(arr, k);
        return (res>=0) ? res : -1;
    }
}
```
⚠️
```java
// A custom binary search that finds the first occurrence of k.
import java.util.Arrays;
class Solution {
    public int binarysearch(int[] arr, int k) {
       
class Solution {
    public int binarysearch(int[] arr, int k) {
        int n = arr.length;
       int beg = 0;
       int end = n-1;
       int res = -1;
       while( beg<=end ){
           int mid = (beg+end)/2;
           if (arr[mid] == k) {             
                res = mid;                  // ✅ As we study here should be { return mid }
                end = mid - 1;              // ✅ But there is a problem does not guarantee returning the first index of 
                                            //     a duplicate element.
            }
           else if(k < arr[mid]){
               end = mid-1;
           }
           else{
               beg = mid+1;
           }
       }
       return res;
    }
}
    }
}
```
---
