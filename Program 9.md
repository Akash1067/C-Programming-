#include <stdio.h>

int main() {
    int num, rev = 0;

    printf("Enter an integer: ");
    scanf("%d", &num);

    for (; num != 0; num /= 10) {
        rev = rev * 10 + num % 10;
    }

    printf("The reverse of the integer is: %d\n", rev);

    return 0;
}
