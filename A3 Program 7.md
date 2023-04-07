#include <stdio.h>
#include <string.h>

int main()
{
    char str[100];
    int sum = 0;

    printf("Enter the string : ");
    fgets(str, sizeof(str), stdin);
    
    for (int i = 0; i < strlen(str); i++)
    {
        sum += str[i];
    }
    
    printf("Sum of all characters : %d", sum);

    return 0;
}
