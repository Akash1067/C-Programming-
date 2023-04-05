V#include <stdio.h>

int main() {
    int arr[100];
    int n, i, max1, max2;
    
    printf("Enter the size of the array: ");
    scanf("%d", &n);
    
    printf("Enter the elements of the array:\n");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    max1 = arr[0];
    max2 = arr[1];
    
    for (i = 1; i < n; i++) {
        if (arr[i] > max1) {
            max2 = max1;
            max1 = arr[i];
        }
        else if (arr[i] > max2 && arr[i] != max1) {
            max2 = arr[i];
        }
    }
    
    printf("The largest two elements in the array are: %d and %d\n", max1, max2);
    
    return 0;
}
