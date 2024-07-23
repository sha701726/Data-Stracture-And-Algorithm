# Insertion Sort: An Overview

Insertion sort is a simple and intuitive comparison-based sorting algorithm. It builds the final sorted array one item at a time. It's much like sorting playing cards in your hands: you pick one card and place it in its correct position among the already sorted cards.

## Here’s a detailed explanation of insertion sort:

### Algorithm
1. **Starting Point**: Assume the first element in the array is already sorted.
2. **Iterate**: Take the next element and compare it with the elements in the sorted portion.
3. **Shifting**: Shift all the elements in the sorted portion that are greater than the new element to the right.
4. **Insert**: Place the new element in its correct position.
5. **Repeat**: Repeat steps 2-4 for all elements in the array.

### Steps
1. **Initialization**: Start with the second element (index 1) of the array.
2. **Compare**: Compare the current element with the elements in the sorted portion (to its left).
3. **Shift**: If the current element is smaller than the compared element, shift the compared element to the right.
4. **Insert**: Insert the current element into the correct position.
5. **Repeat**: Move to the next element and repeat the process until the entire array is sorted.

### Example
Consider the array: `[5, 2, 4, 6, 1, 3]`

- **Initial array**: `[5, 2, 4, 6, 1, 3]`

  **Step 1**: Take the second element (2) and compare it with 5. Since 2 < 5, shift 5 to the right and insert 2 at index 0.
  
  **Array**: `[2, 5, 4, 6, 1, 3]`

  **Step 2**: Take the next element (4) and compare it with the sorted portion `[2, 5]`. Since 4 < 5, shift 5 to the right and insert 4 at index 1.
  
  **Array**: `[2, 4, 5, 6, 1, 3]`

  **Step 3**: Take the next element (6) and compare it with the sorted portion `[2, 4, 5]`. Since 6 > 5, it stays in place.
  
  **Array**: `[2, 4, 5, 6, 1, 3]`

  **Step 4**: Take the next element (1) and compare it with the sorted portion `[2, 4, 5, 6]`. Shift 6, 5, 4, and 2 to the right and insert 1 at index 0.
  
  **Array**: `[1, 2, 4, 5, 6, 3]`

  **Step 5**: Take the next element (3) and compare it with the sorted portion `[1, 2, 4, 5, 6]`. Shift 6, 5, and 4 to the right and insert 3 at index 2.
  
  **Array**: `[1, 2, 3, 4, 5, 6]`

### Characteristics

**Time Complexity**:
- **Best Case**: 𝑂(𝑛) when the array is already sorted.
- **Average Case**: 𝑂(𝑛²)
- **Worst Case**: 𝑂(𝑛²) when the array is sorted in reverse order.

**Space Complexity**: 𝑂(1) as it’s an in-place sorting algorithm.

**Stable**: Yes, insertion sort is a stable sort, meaning it preserves the relative order of equal elements.

**Adaptive**: Efficient for data sets that are already substantially sorted: the time complexity is 𝑂(𝑘𝑛) when each element in the input is not more than 𝑘 positions away from its sorted position.


## Pseudocode
Here’s the pseudocode for insertion sort:
```markdown
for i = 1 to length(A) - 1
    key = A[i]
    j = i - 1
    while j >= 0 and A[j] > key
        A[j + 1] = A[j]
        j = j - 1
    A[j + 1] = key
```

## Advantages

- Simple to implement.
- Efficient for small data sets or nearly sorted data.
- In-place and stable.

## Disadvantages

- Inefficient for large data sets.
- Quadratic time complexity in the average and worst cases.

Insertion sort is a useful algorithm in scenarios where the data is nearly sorted or when the dataset is small. It’s also often used as a building block in more complex sorting algorithms.

## C++ Implementation

Here’s a C++ program that implements the insertion sort algorithm. I’ll include comments in the code to explain each step.

C++ Program Of Insertion Sort:
```cpp
#include <iostream>
using namespace std;

// Function to perform insertion sort
void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; ++i) {
        int key = arr[i]; // Element to be inserted
        int j = i - 1;

        // Move elements of arr[0..i-1], that are greater than key,
        // to one position ahead of their current position
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key; // Place the key at its correct position
    }
}

// Function to print the array
void printArray(int arr[], int n) {
    for (int i = 0; i < n; ++i) {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int main() {
    int arr[] = {12, 11, 13, 5, 6};
    int n = sizeof(arr) / sizeof(arr[0]);

    cout << "Original array: ";
    printArray(arr, n);

    insertionSort(arr, n);

    cout << "Sorted array: ";
    printArray(arr, n);

    return 0;
}
```

## Explanation
### Including Libraries:
``` cpp
#include <iostream>
using namespace std;
```
The iostream library is included to use cin and cout for input and output.
Insertion Sort Function:

Insertion Insertion Sort Function: 
```cpp
void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; ++i) {
        int key = arr[i]; // Element to be inserted
        int j = i - 1;

        // Move elements of arr[0..i-1], that are greater than key,
        // to one position ahead of their current position
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key; // Place the key at its correct position
    }
}
```
The outer loop iterates through each element starting from the second element.
key is the current element being inserted into the sorted portion of the array.
The inner loop shifts elements greater than key to the right to make space for the key.
After finding the correct position, key is placed in its correct position.

### Print Array Function:
```cpp
void printArray(int arr[], int n) {
    for (int i = 0; i < n; ++i) {
        cout << arr[i] << " ";
    }
    cout << endl;
}
```
This function prints the array elements.

### Main Function
```cpp
int main() {
    int arr[] = {12, 11, 13, 5, 6};
    int n = sizeof(arr) / sizeof(arr[0]);

    cout << "Original array: ";
    printArray(arr, n);

    insertionSort(arr, n);

    cout << "Sorted array: ";
    printArray(arr, n);

    return 0;
}
```
1. Initializes an array `arr` with some unsorted values.
2. Calculates the size of the array.
3. Prints the original array, sorts it using `insertionSort`, and then prints the sorted array.

### Output
When you run this program, you will see:
```markdown
Original array: 12 11 13 5 6 
Sorted array: 5 6 11 12 13
```
