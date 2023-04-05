#include <stdio.h>

int main() {
    int arr[100], n, i, max1, max2, min1, min2;
    
    printf("Enter the size of the array: ");
    scanf("%d", &n);
    
    printf("Enter the elements of the array:\n");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    max1 = max2 = arr[0];
    min1 = min2 = arr[0];
    
    for (i = 1; i < n; i++) {
        if (arr[i] > max1) {
            max2 = max1;
            max1 = arr[i];
        }
        else if (arr[i] > max2 && arr[i] != max1) {
            max2 = arr[i];
        }
        if (arr[i] < min1) {
            min2 = min1;
            min1 = arr[i];
        }
        else if (arr[i] < min2 && arr[i] != min1) {
            min2 = arr[i];
        }
    }
    
    printf("The second largest element in the array is: %d\n", max2);
    printf("The second smallest element in the array is: %d\n", min2);
    
    return 0;
}
