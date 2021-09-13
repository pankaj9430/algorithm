/* algorithm
  Write a algorithm to sort an array. This question will be graded on the basis of efficiency and coding style
  implementation of sorting array using selection sort.
  Find the smallest number. Swap it with the first number.
  Find the second-smallest number. Swap it with the second number.
  Find the third-smallest number. Swap it with the third number.
  Function to print an array 
  Repeat finding the next-smallest number, and swapping it into the correct position until the array is sorted.
  This algorithm is called selection sort because it repeatedly selects the next-smallest element and swaps it into place.
 
*/

#include <bits/stdc++.h>
using namespace std;
 
void algorithm(int *r, int *s)
{
    int temp = *r;
    *r = *s;
    *s = temp;
}
 
void selectionSort(int arr[], int n)
{
    int i, j, min_idx;
 
   
    for (i = 0; i < n-1; i++)
    {
        
        min_idx = i;
        for (j = i+1; j < n; j++)
        if (arr[j] < arr[min_idx])
            min_idx = j;
 
        
        swap(&arr[min_idx], &arr[i]);
    }
}
 
void printArray(int arr[], int size)
{
    int i;
    for (i=0; i < size; i++)
        cout << arr[i] << " ";
    cout << endl;
}
 

int main()
{
    int arr[] = {83, 1, 45, 95, 45, 52, 11, 47, 0, 45, 67, 82 };
    int n = sizeof(arr)/sizeof(arr[0]);
    selectionSort(arr, n);
    cout << "Sorted array: \n";
    printArray(arr, n);
    return 0;
}
