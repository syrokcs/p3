#include <stdio.h>

int main() {
    int p;
    scanf("%d", &p);

    long long dp0[p+1];
    long long dp1[p+1];

    // Ініціалізація значень
    dp0[2] = 2;
    dp1[2] = 1;

    // Обчислення значень dp0 та dp1
    for (int i = 3; i <= p; i++) {
        dp0[i] = dp0[i-1] + dp1[i-1];
        dp1[i] = dp0[i-1];
    }

    // Обчислення кількості чисел
    long long count = dp0[p] + dp1[p];

    printf("Кількість чисел: %lld\n", count);

    return 0;
}
