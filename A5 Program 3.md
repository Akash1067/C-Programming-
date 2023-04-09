#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_LINE_LENGTH 1000

int main() {
    FILE *inputFile, *outputFile;
    char line[MAX_LINE_LENGTH];
    char *match;
    
    // open input file for reading
    inputFile = fopen("input.txt", "r");
    if (inputFile == NULL) {
        printf("Failed to open input file.");
        return 1;
    }
    
    // open output file for writing
    outputFile = fopen("output.txt", "w");
    if (outputFile == NULL) {
        printf("Failed to create output file.");
        fclose(inputFile);
        return 1;
    }
    
    // read each line of input file, replace "red" with "blue", and write to output file
    while (fgets(line, MAX_LINE_LENGTH, inputFile)) {
        while ((match = strstr(line, "red")) != NULL) {
            strncpy(match, "blue", 4);
        }
        fputs(line, outputFile);
    }
    
    // close input and output files
    fclose(inputFile);
    fclose(outputFile);
    
    return 0;
}
