# Quick Sort: An Overview

 Quick Sort is a popular sorting algorithm known for its efficiency and speed. It uses a divide-and-conquer approach to sort elements by selecting a pivot element, partitioning the array around it, and recursively sorting the subarrays.

### How Quick Sort Works

1. Choose a Pivot: Select an element from the array to serve as the pivot.
2. Partition: Rearrange the array so that all elements less than the pivot are on its left, and all elements greater are on its right.
3. Recursively Sort: Apply the quick sort algorithm to the subarray of elements less than the pivot and the subarray of elements greater than the pivot.

### Pseudocode for Quick Sort
    
    procedure quickSort(A: list of sortable items)
        if length(A) ≤ 1 then
        return A
    else
        pivot := choosePivot(A)
        left := [x ∈ A | x ≤ pivot]
        right := [x ∈ A | x > pivot]
        return quickSort(left) + pivot + quickSort(right)


### Example:
Consider sorting the array [5, 1, 4, 2, 8] using quick sort:
 First Call:
- Choose pivot 5
- Partition: [1, 4, 2] | 5 | [8]
- Recursively sort [1, 4, 2] and [8]

Second Call (left):
- Choose pivot 1
- Partition: [] | 1 | [4, 2]
- Recursively sort [4, 2]

Third Call (left-left):
- Choose pivot 4
- Partition: [2] | 4 | []
- Recursively sort [2]

Fourth Call (left-left-left):
- Return [2] (already sorted)

Fifth Call (left-left-right):
- Return [4] (already sorted)

Sixth Call (left-right):
- Return [1, 2, 4] (sorted)

Seventh Call (right):
- Return [8] (already sorted)

Final Result:
[1, 2, 4, 5, 8] (sorted)

### Characteristics of Quick Sort

Time Complexity:
- Worst-case: O(n^2)
- Best-case: O(n log n)
- Average-case: O(n log n)

Space Complexity: O(log n) (recursive call stack)
Stability: No, quick sort is not a stable sort (it may swap equal elements)
Adaptive: No, quick sort always performs the same number of operations
### Advantages and Disadvantages

Advantages:
- Fast and efficient for large datasets
- In-place sort, no extra memory required

Disadvantages:
- Worst-case performance is poor (O(n^2))
- Not stable, may swap equal elements

### Conclusion
Quick sort is a powerful and widely used sorting algorithm. Its average-case performance is excellent, making it suitable for large datasets. However, its worst-case performance and instability may make other algorithms more suitable for certain use cases.

An Example Of Quick Sort Demonstration In C++ Language:

    #include <iostream>
    using namespace std;

// Function to swap two elements
    
    void swap(int &a, int &b){
        int temp = a;
        a = b;
        b = temp;
    }
    
// Function to partition the array

    int partition(int arr[], int low, int high){
        int pivot = arr[high];
        int i = (low - 1);
        for (int j = low; j <= high - 1; j++) {
            if (arr[j] < pivot)
            {
                i++;
                swap(arr[i], arr[j]);
            }
        }
    swap(arr[i + 1], arr[high]);
    return (i + 1);
    }

// Function to perform Quick Sort

    void quickSort(int arr[], int low, int high) {
        if (low < high)
        {
            int pivot = partition(arr, low, high);
            quickSort(arr, low, pivot - 1);
            quickSort(arr, pivot + 1, high);
        }
    }
    
// Function to print an array

    void printArray(int arr[], int size) {
        for (int i = 0; i < size; i++)
        cout << arr[i] << " ";
        cout << endl;
    }

//Main Function starts From Here
    
    int main() {
        int arr[] = {64, 34, 25, 12, 22, 11, 90};
        int n = sizeof(arr) / sizeof(arr[0]);
        cout << "Unsorted array: ";
        printArray(arr, n);
        quickSort(arr, 0, n - 1);
        cout << "Sorted array: ";
        printArray(arr, n);
        return 0;
    }