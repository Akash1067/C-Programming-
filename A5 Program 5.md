#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <ctype.h>

#define ALPHABET_SIZE 26

int main() {
    FILE *dataFile, *statsFile;
    char dataFilename[] = "data.txt";
    char statsFilename[] = "statistics.txt";
    int freq[ALPHABET_SIZE] = {0};
    int c;
    
    // open data file for reading
    dataFile = fopen(dataFilename, "r");
    if (dataFile == NULL) {
        printf("Failed to open data file.");
        return 1;
    }
    
    // read each character from data file and update frequency count
    while ((c = fgetc(dataFile)) != EOF) {
        if (isalpha(c)) {
            freq[tolower(c) - 'a']++;
        }
    }
    
    // close data file
    fclose(dataFile);
    
    // open stats file for writing
    statsFile = fopen(statsFilename, "w");
    if (statsFile == NULL) {
        printf("Failed to create statistics file.");
        return 1;
    }
    
    // write frequency counts to stats file
    for (int i = 0; i < ALPHABET_SIZE; i++) {
        fprintf(statsFile, "%c: %d\n", i + 'a', freq[i]);
    }
    
    // close stats file
    fclose(statsFile);
    
    return 0;
}
