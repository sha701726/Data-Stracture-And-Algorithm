##Selection Sort Ovreview

Selection sort is a comparison-based sorting algorithm that divides the list into a sorted and an unsorted sublist. It repeatedly selects the smallest (or largest) element from the unsorted sublist and swaps it with the leftmost unsorted element, gradually building the sorted sublist.

### How Selection Sort Works

Selection sort works by dividing the input list into two parts: a sorted sublist of items which is built up from left to right at the front (left) of the list, and a sublist of the remaining unsorted items. Initially, the sorted sublist is empty, and the unsorted sublist is the entire input list. The algorithm proceeds by finding the smallest (or largest, depending on the order) element from the unsorted sublist, swapping it with the leftmost unsorted element (putting it in sorted order), and moving the sublist boundaries one element to the right.

### Steps of the Algorithm

1. **Initialize** the sorted sublist as empty and the unsorted sublist as the entire list.
2. **Find the minimum (or maximum)** element in the unsorted sublist.
3. **Swap** the found minimum (or maximum) element with the first element of the unsorted sublist.
4. **Move** the boundary between the sorted and unsorted sublists one element to the right.
5. Repeat steps 2-4 until the entire list is sorted.

### Pseudocode

Here is a pseudocode representation of selection sort:

```
for i = 0 to n-1
    min_index = i
    for j = i+1 to n
        if list[j] < list[min_index]
            min_index = j
    if min_index != i
        swap list[i] and list[min_index]
```

### Example

Let's sort the list [64, 25, 12, 22, 11]:

1. Initial list: [64, 25, 12, 22, 11]
2. Find the minimum element in the entire list, which is 11, and swap it with the first element: [11, 25, 12, 22, 64]
3. Find the minimum element in the remaining unsorted sublist [25, 12, 22, 64], which is 12, and swap it with the first element of this sublist: [11, 12, 25, 22, 64]
4. Find the minimum element in the remaining unsorted sublist [25, 22, 64], which is 22, and swap it with the first element of this sublist: [11, 12, 22, 25, 64]
5. Find the minimum element in the remaining unsorted sublist [25, 64], which is 25, and it is already in the correct position: [11, 12, 22, 25, 64]
6. The list is now sorted.

### Time Complexity

**Best case**: O(n^2)
**Average case**: O(n^2)
**Worst case**: O(n^2)

### Space Complexity

**Auxiliary Space**: O(1) (Selection sort is an in-place sorting algorithm)

### Characteristics

**In-place**: Yes, it does not require extra storage space.
**Stable**: No, selection sort is not stable. Equal elements might not maintain their relative order.
**Adaptive**: No, selection sort does not adapt to the input.

### Practical Use

Selection sort is not suitable for large datasets as it has a time complexity of O(n^2). It is often used when the list is small or when the cost of swapping elements is low.

### Comparison with Other Sorting Algorithms

**Bubble Sort**: Both have a time complexity of O(n^2), but bubble sort repeatedly swaps adjacent elements and is often considered less efficient than selection sort.
**Insertion Sort**: Also O(n^2) in the average and worst cases, but it is more efficient for nearly sorted data.
**Quick Sort and Merge Sort**: More efficient for large datasets with average time complexities of O(n log n).


### Here is a simple C++ program that implements the selection sort algorithm:

```cpp
#include <iostream>
#include <vector>

using namespace std;

// Function to perform selection sort on an array
void selectionSort(vector<int>& arr) {
    int n = arr.size();

    for (int i = 0; i < n - 1; i++) {
        // Find the index of the minimum element in the unsorted part
        int minIndex = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }

        // Swap the found minimum element with the first element of the unsorted part
        if (minIndex != i) {
            swap(arr[i], arr[minIndex]);
        }
    }
}

// Function to print an array
void printArray(const vector<int>& arr) {
    for (int i = 0; i < arr.size(); i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int main() {
    vector<int> arr = {64, 25, 12, 22, 11};

    cout << "Original array: ";
    printArray(arr);

    selectionSort(arr);

    cout << "Sorted array: ";
    printArray(arr);

    return 0;
}
```

### Explanation:

1. **Includes and using namespace**:
   - `#include <iostream>` is for input-output operations.
   - `#include <vector>` is for using the `vector` container.
   - `using namespace std` allows us to use standard library objects and functions without prefixing them with `std::`.

2. **Selection Sort Function**:
   - The function `selectionSort` takes a reference to a vector of integers and sorts it in ascending order.
   - The outer loop iterates through each element of the array except the last one.
   - The inner loop finds the index of the minimum element in the unsorted part of the array.
   - After finding the minimum element, it swaps it with the first element of the unsorted part if needed.

3. **Print Array Function**:
   - The function `printArray` takes a constant reference to a vector of integers and prints its elements.

4. **Main Function**:
   - A vector `arr` is defined and initialized with unsorted values.
   - The original array is printed.
   - The `selectionSort` function is called to sort the array.
   - The sorted array is printed.

This program demonstrates how selection sort works in C++ by sorting an example array.
