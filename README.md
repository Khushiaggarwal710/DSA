# Important Questions of DSA
## BASIC QUESTIONS:-
<br>

### 1. Find the Largest element in an array
<br>

#### ✨ Example 1:

**Input:**
<br>
 arr[] = {2,5,1,3,0};<br>
**Output:**
 5<br>
 
**Explanation:**
 5 is the largest element in the array. 

### ✨ Example 2:
**Input:**<br>
 arr[] = {8,10,5,7,9};<br>
**Output:**
 10<br>
 
**Explanation:**
 10 is the largest element in the array.

```bash
    
#include <bits/stdc++.h>
 
using namespace std;
int findLargestElement(int arr[], int n) {
 
  int max = arr[0];
  for (int i = 0; i < n; i++) {
    if (max < arr[i]) {
      max = arr[i];
    }
  }
  return max;
}
int main() {
  int arr1[] = {2,5,1,3,0};
  int n = 5;
  int max = findLargestElement(arr1, n);
  cout << "The largest element in the array is: " << max << endl;
 
  int arr2[] =  {8,10,5,7,9};
  n = 5;
  max = findLargestElement(arr2, n);
  cout << "The largest element in the array is: " << max<<endl;
  return 0;
}

```
#### ✨ Complexity Analysis:

**Time Complexity:** O(N), where N is the size of the array (as we traverse the array once).

**Space Complexity:** O(1), as we use a constant amount of extra space.

<br>

___

### 2. Find Second Smallest and Second Largest Element in an array
<br>

### ✨ Example 1:

**Input:**

**arr[] = {1,2,4,7,7,5}**

**Output:**
<br>

**Second Smallest : 2**
<br>
**Second Largest : 5**

### Explanation:
 Since there is only one element in the array, it is the largest and smallest element present in the array. There is no second largest or second smallest element present.
 ```bash



#include<bits/stdc++.h>
using namespace std;
int secondSmallest(int arr[],int n)
{
    if(n<2)
        return -1;
    int small = INT_MAX;
    int second_small = INT_MAX;
    int i;
    for(i = 0; i < n; i++) 
    {
       if(arr[i] < small)
       {
          second_small = small;
          small = arr[i];
       }
       else if(arr[i] < second_small && arr[i] != small)
       {
          second_small = arr[i];
       }
    }
   return second_small;     
}
int secondLargest(int arr[],int n)
{
	if(n<2)
	return -1;
    int large=INT_MIN,second_large=INT_MIN;
    int i;
    for (i = 0; i < n; i++) 
    {
        if (arr[i] > large) 
        {
            second_large = large;
            large = arr[i];
        }
 
        else if (arr[i] > second_large && arr[i] != large) 
        {
            second_large = arr[i];
        }
    }
    return second_large;                
}

int main() {
    int arr[]={1,2,4,7,7,5};  
    int n=sizeof(arr)/sizeof(arr[0]);
        int sS=secondSmallest(arr,n);
        int sL=secondLargest(arr,n);
    cout<<"Second smallest is "<<sS<<endl;
    cout<<"Second largest is "<<sL<<endl;
    return 0;
}

```
**Time Complexity: O(N), Single-pass solution**

**Space Complexity: O(1)**

<br>
___
### 3. Remove Duplicates in-place from Sorted Array
<br>

**Problem Statement:**
Given an integer array sorted in non-decreasing order, remove the duplicates in place such that each unique element appears only once. The relative order of the elements should be kept the same.

If there are k elements after removing the duplicates, then the first k elements of the array should hold the final result. It does not matter what you leave beyond the first k elements.

**Note:** Return k after placing the final result in the first k slots of the array.

### ✨ Example 1:

**arr = {1,1,2,2,2,3,3}**

**Output:**

 **arr = [1,2,3,_,_,_,_,_]**
<br>

```bash


#include<bits/stdc++.h>

using namespace std;
int removeDuplicates(int arr[], int n)
{
  int i = 0;
  for (int j = 1; j < n; j++) {
    if (arr[i] != arr[j]) {
      i++;
      arr[i] = arr[j];
    }
  }
  return i + 1;
}
int main() {
  int arr[] = {1,1,2,2,2,3,3};
  int n = sizeof(arr)/sizeof(arr[0]);
  int k = removeDuplicates(arr, n);
  cout << "The array after removing duplicate elements is " << endl;
  for (int i = 0; i < k; i++) {
    cout << arr[i] << " ";
  }
}

```
**Complexity Analysis**

**Time Complexity: O(N)**

**Space Complexity: O(1)**
___




