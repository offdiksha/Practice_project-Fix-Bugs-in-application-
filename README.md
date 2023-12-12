package com.FourthAssignment;


import java.util.Arrays;
 
public class BugFixingApplication {
 
    // Task 1: Searching Technique
    // Implementing binary search
    public static int binarySearch(int[] array, int target) {
        int low = 0;
        int high = array.length - 1;
 
        while (low <= high) {
            int mid = low + (high - low) / 2;
 
            if (array[mid] == target) {
                return mid; // Target found
            } else if (array[mid] < target) {
                low = mid + 1; // Search in the right half
            } else {
                high = mid - 1; // Search in the left half
            }
        }
 
        return -1; // Target not found
    }
 
    // Task 2: Sorting the Predefined Array
    // Implementing quicksort
    public static void quicksort(int[] array, int low, int high) {
        if (low < high) {
            int pivotIndex = partition(array, low, high);
 
            quicksort(array, low, pivotIndex - 1);
            quicksort(array, pivotIndex + 1, high);
        }
    }
 
    private static int partition(int[] array, int low, int high) {
        int pivot = array[high];
        int i = low - 1;
 
        for (int j = low; j < high; j++) {
            if (array[j] <= pivot) {
                i++;
                swap(array, i, j);
            }
        }
 
        swap(array, i + 1, high);
        return i + 1;
    }
 
    private static void swap(int[] array, int i, int j) {
        int temp = array[i];
        array[i] = array[j];
        array[j] = temp;
    }
 
    public static void main(String[] args) {
        // Example array
        int[] array = {5, 2, 8, 1, 6, 3, 7, 4};
 
        // Task 1: Searching Technique
        int target = 6;
        int searchResult = binarySearch(array, target);
        System.out.println("Search Result: " + searchResult);
 
        // Task 2: Sorting the Predefined Array
        quicksort(array, 0, array.length - 1);
        System.out.println("Sorted Array: " + Arrays.toString(array));
    }
}
