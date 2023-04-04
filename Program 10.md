#include <stdio.h>

int main() {
    int dec, rem, i = 0;
    int bin[32]; // array to store binary digits

    printf("Enter a decimal number: ");
    scanf("%d", &dec);

    // convert decimal to binary
    while (dec > 0) {
        rem = dec % 2;
        bin[i++] = rem;
        dec /= 2;
    }

    // print binary number in reverse order
    printf("The binary equivalent is: ");
    for (int j = i - 1; j >= 0; j--) {
        printf("%d", bin[j]);
    }
    printf("\n");

    return 0;
}
