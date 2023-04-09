#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_LINE_LENGTH 1000

int main() {
    FILE *input_file, *error_file;
    char line[MAX_LINE_LENGTH];

    // Open input file for reading
    input_file = fopen("input.txt", "r");
    if (input_file == NULL) {
        printf("Error opening input file\n");
        exit(1);
    }

    // Open error log file for writing
    error_file = fopen("error_log.txt", "w");
    if (error_file == NULL) {
        printf("Error opening error log file\n");
        exit(1);
    }

    // Loop over each line in the input file
    while (fgets(line, MAX_LINE_LENGTH, input_file)) {
        // If the line contains the word "error"
        if (strstr(line, "error") != NULL) {
            // Write the line to the error log file
            fputs(line, error_file);
        }
    }

    // Close input and error files
    fclose(input_file);
    fclose(error_file);

    // Open error log file for reading
    error_file = fopen("error_log.txt", "r");
    if (error_file == NULL) {
        printf("Error opening error log file\n");
        exit(1);
    }

    // Loop over each line in the error log file
    while (fgets(line, MAX_LINE_LENGTH, error_file)) {
        // Print the line to the console
        printf("%s", line);
    }

    // Close error file
    fclose(error_file);

    return 0;
}
