# Merge Sort
Perform Merge Sort using JAVA language.

# About Merge Sort
Merge sort is the sorting technique that follows the divide and conquer approach.It is one of the most popular and efficient sorting algorithm. It divides the
given list into two equal halves, calls itself for the two halves and then merges the two sorted halves. We have to define the merge() function to perform the merging.

The sub-lists are divided again and again into halves until the list cannot be divided further. Then we combine the pair of one element lists into two-element lists,
sorting them in the process. The sorted two-element pairs is merged into the four-element lists, and so on until we get the sorted list.

![Merge-sort](https://user-images.githubusercontent.com/35636662/143670816-0d01537f-3a33-4905-9484-f2bd5582dfd7.gif)


# Java
   Step 1: 
         
        // Create left ← A[p..q] and right ← A[q+1..r]
        int n1 = q - p + 1;
        int n2 = r - q;

       int left[] = new int[n1];
       int rightM[] = new int[n2];

       for (int i = 0; i < n1; i++)
       left[i] = arr[p + i];
       for (int j = 0; j < n2; j++)
       rightM[j] = arr[q + 1 + j];
 
  Step 2: Maintain current index of sub-arrays and main array
    
         int i, j, k;
         i = 0; 
         j = 0; 
         k = p; 
         
 Step 3: Until we reach the end of either left or right, pick larger among elements left and right and place them in the correct position at A[p..r]
    
        while (i < n1 && j < n2) { 
        if (left[i] <= M[j]) { 
            arr[k] = left[i]; i++; 
        } 
        else { 
            arr[k] = M[j]; 
            j++; 
        } 
        k++; 
       }   
       
 Step 4: When we run out of elements in either L or M, pick up the remaining elements and put in A[p..r]
   
      while (i < n1) {
      arr[k] = L[i];
      i++;
      k++;
     }

     while (j < n2) {
      arr[k] = M[j];
      j++;
      k++;
     }   
     
 Step 5: Divide the array into two subarrays, sort them and merge them
  
     void mergeSort(int arr[], int l, int r) {
     if (l < r) {
      // m is the point where the array is divided into two subarrays
      int m = (l + r) / 2;

      mergeSort(arr, l, m);
      mergeSort(arr, m + 1, r);

      // Merge the sorted subarrays
      merge(arr, l, m, r);
    }
    }  
    
Step 6: Create object and call the method with array,array size and start=0    

    int numbers[] = {15, 2, 13, 4, 8, 10, 50, 40};
    Merge_Sort obj = new Merge_Sort();
    obj.mergeSort(numbers, 0, numbers.length - 1);
    
      Step 2: 
Step 7: Now,Print sorted Array in Ascending Order by loop
   
            System.out.print("Sorted Array in Ascending Order: ");
            for (int i = 0; i < numbers.length; i++) {
            System.out.print(numbers[i] + " ");
            }
