#include <stdio.h>

int main() {
    int arr[100];
    int freq[100];
    int n, i, j, count;
    
    printf("Enter the size of the array: ");
    scanf("%d", &n);
    
    printf("Enter the elements of the array:\n");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        freq[i] = -1; // Initialize frequency count to -1
    }
    
    // Count frequency of each element
    for (i = 0; i < n; i++) {
        count = 1;
        for (j = i+1; j < n; j++) {
            if (arr[i] == arr[j]) {
                count++;
                freq[j] = 0; // Mark as visited
            }
        }
        if (freq[i] != 0) {
            freq[i] = count;
        }
    }
    
    // Print frequency of each element
    printf("\nFrequency of each element in the array:\n");
    for (i = 0; i < n; i++) {
        if (freq[i] != 0) {
            printf("%d occurs %d time(s)\n", arr[i], freq[i]);
        }
    }
    
    return 0;
}
