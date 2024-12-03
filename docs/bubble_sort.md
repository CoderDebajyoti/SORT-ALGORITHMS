## Bubble Sort
```
Bubble Sort repeatedly compares adjacent elements and swaps them if they are in the wrong order. The process is repeated until the array is sorted.
```
```c
#include <stdio.h>

// Function to implement Bubble Sort
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int swapped = 0; // Flag to detect if a swap occurred
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Swap the elements
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
                swapped = 1;
            }
        }
        // If no two elements were swapped in the inner loop, array is sorted
        if (!swapped)
            break;
    }
}

// Function to print an array
void printArray(int arr[], int n) {
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
}

int main() {
    int arr[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(arr) / sizeof(arr[0]);

    printf("Original array: ");
    printArray(arr, n);

    bubbleSort(arr, n);

    printf("Sorted array: ");
    printArray(arr, n);

    return 0;
}
```

### Explanation:
1. **Outer Loop**:
   - Iterates over the entire array `n-1` times.
2. **Inner Loop**:
   - Compares adjacent elements and swaps them if they are out of order.
   - Reduces the range of comparison as the largest elements are placed at the end after each pass.
3. **Optimization with `swapped`**:
   - If no swaps occur during a pass, the array is already sorted, and the algorithm terminates early.
4. **Printing the Array**:
   - A helper function is used to print the elements of the array.

### Sample Output:
```
Original array: 64 34 25 12 22 11 90 
Sorted array: 11 12 22 25 34 64 90 
```