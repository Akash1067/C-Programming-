#include <stdio.h>

#define PI 3.14159265359

union shape {
    float radius;
    struct {
        float length;
        float width;
    } rectangle;
};

int main() {
    union shape s;
    char choice;

    printf("Enter 'c' for circle or 'r' for rectangle: ");
    scanf("%c", &choice);

    if (choice == 'c') {
        printf("Enter the radius of the circle: ");
        scanf("%f", &s.radius);
        printf("Area of the circle: %.2f\n", PI * s.radius * s.radius);
    } else if (choice == 'r') {
        printf("Enter the length of the rectangle: ");
        scanf("%f", &s.rectangle.length);
        printf("Enter the width of the rectangle: ");
        scanf("%f", &s.rectangle.width);
        printf("Area of the rectangle: %.2f\n", s.rectangle.length * s.rectangle.width);
    } else {
        printf("Invalid choice.\n");
    }

    return 0;
}
