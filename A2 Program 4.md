#include <stdio.h>
#include <limits.h>

int main() {
    int arr[100], n, i, max_diff, min_val;
    
    printf("Enter the size of the array: ");
    scanf("%d", &n);
    
    printf("Enter the elements of the array:\n");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    max_diff = INT_MIN;  
    min_val = arr[0];
    
    for (i = 1; i < n; i++) {
        if (arr[i] - min_val > max_diff) {
            max_diff = arr[i] - min_val;
        }
        if (arr[i] < min_val) {
            min_val = arr[i];
        }
    }
    
    printf("The maximum difference between two elements in the array is: %d\n", max_diff);
    
    return 0;
}
