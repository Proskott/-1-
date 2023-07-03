#include <conio.h>
#include <locale.h>
// A function for counting the number of digits
int countNumbers(int r) {
    if (r <= 0) {
        return 0;
    }
    if (r == 1) {
        return 2;  // Two options: 5 та 9
    }

    int prevCount = 2;  // The number of digits for the previous digit
    int totalCount = 2; // Total number of numbers

    for (int i = 2; i <= r; i++) {
        int currentCount = prevCount + totalCount;  // The number of digits for the current digit
        prevCount = totalCount;
        totalCount = currentCount;
    }

    return totalCount;
}

int main() {
    int r;
    printf("Введіть розряд чисел (р): ");
    scanf("%d", &r);

    int count = countNumbers(r);
    printf("Кількість чисел із %d розрядами: %d\n", r, count);

    return 0;
}
