#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *file = fopen("data.bin", "rb"); // open file in binary mode for reading
    if (file == NULL) {
        printf("Failed to open file.");
        return 1;
    }
    
    // determine file size
    fseek(file, 0L, SEEK_END);
    long fileSize = ftell(file);
    fseek(file, 0L, SEEK_SET);
    
    // allocate buffer for file data
    char *buffer = malloc(fileSize);
    if (buffer == NULL) {
        printf("Failed to allocate memory.");
        return 1;
    }
    
    // read file data into buffer
    fread(buffer, fileSize, 1, file);
    fclose(file);
    
    // print file data in human-readable format
    for (int i = 0; i < fileSize; i++) {
        printf("%c", buffer[i]);
    }
    
    free(buffer);
    return 0;
}
