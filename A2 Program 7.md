#include <stdio.h>

int main() {
    int arr[100], reversed_arr[100];
    int n, i, j;
    
    printf("Enter the size of the array: ");
    scanf("%d", &n);
    
    printf("Enter the elements of the array:\n");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    // Reverse the array
    for (i = n-1, j = 0; i >= 0; i--, j++) {
        reversed_arr[j] = arr[i];
    }
    
    printf("\nInput array: ");
    for (i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    printf("\nReversed array: ");
    for (i = 0; i < n; i++) {
        printf("%d ", reversed_arr[i]);
    }
    
    return 0;
}
