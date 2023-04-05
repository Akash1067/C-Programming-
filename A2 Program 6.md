#include <stdio.h>

int main() {
    int arr[100], even[100], odd[100];
    int n, i, j = 0, k = 0;
    
    printf("Enter the size of the array: ");
    scanf("%d", &n);
    
    printf("Enter the elements of the array:\n");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    for (i = 0; i < n; i++) {
        if (arr[i] % 2 == 0) {
            even[j] = arr[i];
            j++;
        }
        else {
            odd[k] = arr[i];
            k++;
        }
    }
    
    printf("\nEven elements: ");
    for (i = 0; i < j; i++) {
        printf("%d ", even[i]);
    }
    
    printf("\nOdd elements: ");
    for (i = 0; i < k; i++) {
        printf("%d ", odd[i]);
    }
    
    return 0;
}
