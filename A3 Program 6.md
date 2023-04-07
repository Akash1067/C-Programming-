#include <stdio.h>
#include <string.h>

#define MAX_SIZE 100

int main()
{
    char str1[MAX_SIZE], str2[MAX_SIZE];
    int freq1[26] = {0}, freq2[26] = {0};
    int i, len1, len2;

    printf("Enter first string: ");
    gets(str1);

    printf("Enter second string: ");
    gets(str2);

    len1 = strlen(str1);
    len2 = strlen(str2);
    
    if (len1 != len2)
    {
        printf("%s and %s are not anagrams.\n", str1, str2);
        return 0;
    }

    
    for (i = 0; i < len1; i++)
    {
        freq1[str1[i] - 'a']++;
    }

  
    for (i = 0; i < len2; i++)
    {
        freq2[str2[i] - 'a']++;
    }

    for (i = 0; i < 26; i++)
    {
        if (freq1[i] != freq2[i])
        {
            printf("%s and %s are not anagrams.\n", str1, str2);
            return 0;
        }
    }

    printf("%s and %s are anagrams.\n", str1, str2);

    return 0;
}
