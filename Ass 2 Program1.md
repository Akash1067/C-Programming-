#include <stdio.h>

int main() {
    int intArr[5] = {12, 56, 34, 78, 100};
    int max = intArr[0];
    int i;
    
    for (i = 1; i < 5; i++) {
        if (intArr[i] > max) {
            max = intArr[i];
        }
    }
    
    printf("The largest element in the array is: %d\n", max);
    
    return 0;
}
