#include <stdio.h>

int main()
{
    int array1[10], array2[10];
    int i, *p1, *p2;

    printf("Input array1 elements: ");
    for (i = 0; i < 10; i++)
        scanf("%d", &array1[i]);

    p1 = array1;
    p2 = array2;

    for (i = 0; i < 10; i++)
        *(p2 + i) = *(p1 + i);

    printf("Array1: ");
    for (i = 0; i < 10; i++)
        printf("%d ", array1[i]);

    printf("\nArray2: ");
    for (i = 0; i < 10; i++)
        printf("%d ", array2[i]);

    return 0;
}
