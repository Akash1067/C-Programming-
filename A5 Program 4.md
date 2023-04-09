#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_LINE_LENGTH 1000

int main() {
    FILE *file;
    char filename[MAX_LINE_LENGTH];
    char searchStr[MAX_LINE_LENGTH];
    char line[MAX_LINE_LENGTH];
    char *match;
    
    // prompt user for file name and search string
    printf("Enter the file name: ");
    fgets(filename, MAX_LINE_LENGTH, stdin);
    filename[strcspn(filename, "\n")] = 0; // remove newline character
    
    printf("Enter the search string: ");
    fgets(searchStr, MAX_LINE_LENGTH, stdin);
    searchStr[strcspn(searchStr, "\n")] = 0; // remove newline character
    
    // open file for reading
    file = fopen(filename, "r");
    if (file == NULL) {
        printf("Failed to open file.");
        return 1;
    }
    
    // read each line of file, search for search string, and print if found
    while (fgets(line, MAX_LINE_LENGTH, file)) {
        if ((match = strstr(line, searchStr)) != NULL) {
            printf("%s", line);
        }
    }
    
    // close file
    fclose(file);
    
    return 0;
}
