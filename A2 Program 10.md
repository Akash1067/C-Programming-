#include <stdio.h>

int minJumps(int arr[], int n) {
    if (n <= 1)
        return 0;

    if (arr[0] == 0)
        return -1;

    int maxReach = arr[0], steps = arr[0], jumps = 1, i;

    for (i = 1; i < n; i++) {
        if (i == n-1)
            return jumps;

        maxReach = (maxReach > i + arr[i]) ? maxReach : i + arr[i];
        steps--;

        if (steps == 0) {
            jumps++;

            if (i >= maxReach)
                return -1;

            steps = maxReach - i;
        }
    }

    return -1;
}

int main() {
    int arr[] = {1, 3, 5, 8, 9, 2, 6, 7, 6, 8, 9};
    int n = sizeof(arr) / sizeof(arr[0]);
    int min_jumps = minJumps(arr, n);

    if (min_jumps == -1)
        printf("It is not possible to reach the end of the array.");
    else
        printf("The minimum number of jumps to reach the end of the array is: %d", min_jumps);

    return 0;
}
