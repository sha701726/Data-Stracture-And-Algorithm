# Bubble Sort: An Overview

Bubble Sort is one of the simplest sorting algorithms. It repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. This process is repeated until the list is sorted.

## How Bubble Sort Works

1. **Compare and Swap**: Starting from the beginning of the list, compare the first two elements. If the first element is greater than the second, swap them. If not, move to the next pair and repeat the process.
2. **Passes**: Each pass through the list places the next largest value in its correct position. After the first pass, the largest element is in the last position. After the second pass, the second largest element is in the second last position, and so on.
3. **Repeat**: Continue this process for all elements in the list. With each pass, the number of comparisons reduces by one, as the last elements are already sorted.

## Pseudocode for Bubble Sort

```plaintext
procedure bubbleSort(A: list of sortable items)
   n := length(A)
   repeat
     swapped := false
     for i := 1 to n - 1 inclusive do
       if A[i - 1] > A[i] then
         swap(A[i - 1], A[i])
         swapped := true
       end if
     end for
     n := n - 1
   until not swapped
end procedure
```

## Example

Consider sorting the array [5, 1, 4, 2, 8] using bubble sort:

### First Pass:
- Compare 5 and 1: swap → [1, 5, 4, 2, 8]
- Compare 5 and 4: swap → [1, 4, 5, 2, 8]
- Compare 5 and 2: swap → [1, 4, 2, 5, 8]
- Compare 5 and 8: no swap → [1, 4, 2, 5, 8]

### Second Pass:
- Compare 1 and 4: no swap → [1, 4, 2, 5, 8]
- Compare 4 and 2: swap → [1, 2, 4, 5, 8]
- Compare 4 and 5: no swap → [1, 2, 4, 5, 8]
- Compare 5 and 8: no swap → [1, 2, 4, 5, 8]

### Third Pass:
- Compare 1 and 2: no swap → [1, 2, 4, 5, 8]
- Compare 2 and 4: no swap → [1, 2, 4, 5, 8]
- Compare 4 and 5: no swap → [1, 2, 4, 5, 8]

The array is now sorted after three passes.

## Characteristics of Bubble Sort

**Time Complexity:**
- Worst-case: O(n^2)
- Best-case: O(n) (when the array is already sorted)
- Average-case: O(n^2)

**Space Complexity:** O(1) (in-place sort, no extra memory required)

**Stability:** Yes, bubble sort is a stable sort (it maintains the relative order of equal elements).

**Adaptive:** In its optimized version, if no elements were swapped in a pass, the algorithm terminates early. This makes it adaptive to a nearly sorted array.

## Advantages and Disadvantages

**Advantages:**
- Simple to implement and understand.
- No additional memory is needed.
- Performs well on small or nearly sorted datasets.

**Disadvantages:**
- Inefficient on large datasets due to its quadratic time complexity.
- Many comparisons and swaps, leading to higher computational cost.

## Conclusion

Bubble sort is a fundamental algorithm in computer science. Despite its inefficiency for large lists, its simplicity makes it a useful educational tool for understanding basic sorting principles and algorithm analysis.

## An Example Of Bubble Sort Demonstration In C++ Language:

```cpp
#include <iostream>
using namespace std;

// Function to swap two elements
void swap(int &a, int &b) {
    int temp = a;
    a = b;
    b = temp;
}

// Function to perform Bubble Sort
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        // Last i elements are already sorted
        bool swapped = false;
        for (int j = 0; j < n - i - 1; j++) {
            // If the element found is greater than the next element, swap them
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
                swapped = true;
            }
        }
        // If no two elements were swapped by inner loop, then break
        if (!swapped)
            break;
    }
}

// Function to print an array
void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++)
        cout << arr[i] << " ";
    cout << endl;
}

int main() {
    int arr[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(arr) / sizeof(arr[0]);
    cout << "Unsorted array: ";
    printArray(arr, n);
    bubbleSort(arr, n);
    cout << "Sorted array: ";
    printArray(arr, n);
    return 0;
}
```

## Explanation

### Swap Function
This function swaps two elements using a temporary variable.

### Bubble Sort Function
- It takes an array and its size `n` as arguments.
- The outer loop iterates over each element except the last sorted ones.
- The inner loop compares each pair of adjacent elements and swaps them if they are in the wrong order.
- The swapped flag is used to detect if any swaps were made during the inner loop. If no swaps were made, the array is already sorted, and the loop can be terminated early.

### Print Array Function
This function prints the elements of the array.

### Main Function
- An example array is defined and printed in its unsorted state.
- The `bubbleSort` function is called to sort the array.
- The sorted array is printed.

### Output
When you run this program, you should get the following output:

```plaintext
Unsorted array: 64 34 25 12 22 11 90 
Sorted array: 11 12 22 25 34 64 90 
```
This demonstrates how bubble sort sorts the array step-by-step.