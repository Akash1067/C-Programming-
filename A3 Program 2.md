#include <stdio.h>

int isPrime(int n) {
    int i;
    for (i = 2; i <= n / 2; ++i) {
        if (n % i == 0) {
            return 0;
        }
    }
    return 1;
}

int main() {
    int n, i, flag = 0;
    printf("Enter a positive integer: ");
    scanf("%d", &n);
    for (i = 2; i <= n / 2; ++i) {
        if (isPrime(i)) {
            if (isPrime(n - i)) {
                printf("%d = %d + %d\n", n, i, n - i);
                flag = 1;
            }
        }
    }
    if (flag == 0) {
        printf("%d cannot be expressed as the sum of two prime numbers\n", n);
    }
    return 0;
}
