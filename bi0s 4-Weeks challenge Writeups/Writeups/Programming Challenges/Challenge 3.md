# Challenge 3

```c
#include <stdio.h>

int main() {
    int n, x;
    printf("Enter the value of n: ");
    scanf("%d", &n);
    printf("Enter the value of x: ");
    scanf("%d", &x);

    int f = 0;
    int s = 1;
    int fib[n + x];
    fib[0] = f;
    fib[1] = s;
    int count = 2;

    while (count < n + x) {
        int t = f + s;
        fib[count] = t;
        f = s;
        s = t;
        count++;
    }

    for (int i = n - 1; i < n + x - 1; i++) {
        printf("%d ", fib[i]);
    }
    printf("\n");

    return 0;
}
```