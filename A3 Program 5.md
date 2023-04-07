#include <stdio.h>
#include <string.h>

#define MAX_SIZE 100

int main()
{
    char str[MAX_SIZE];
    int freq[256] = {0}; // Initialize frequency array with 0
    int i, maxFreq, len;

    printf("Enter a string: ");
    fgets(str, MAX_SIZE, stdin);

    len = strlen(str);

    // Count frequency of each character
    for(i = 0; i < len; i++)
    {
        freq[str[i]]++;
    }

    maxFreq = freq[str[0]];
    for(i = 0; i < len; i++)
    {
        if(freq[str[i]] > maxFreq)
        {
            maxFreq = freq[str[i]];
        }
    }

    // Print highest frequency characters
    printf("Max repeated character in the string = ");
    for(i = 0; i < len; i++)
    {
        if(freq[str[i]] == maxFreq)
        {
            printf("%c ", str[i]);
        }
    }
    printf("\nIt occurs %d times", maxFreq);

    return 0;
}
