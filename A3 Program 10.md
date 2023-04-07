#include <stdio.h>

void reverse_string(char* str);

int main() {
    char str[100];
    printf("Enter any string: ");
    scanf("%s", str);
    reverse_string(str);
    printf("The reverse of the string [%s] is :: %s", str, str);
    return 0;
}

void reverse_string(char* str) {
    char* start = str;
    char* end = str;
    char temp;
    while (*end != '\0') {
        end++;
    }
    end--;
    while (start < end) {
        temp = *start;
        *start = *end;
        *end = temp;
        start++;
        end--;
    }
}
