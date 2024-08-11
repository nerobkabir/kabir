# Simple calculator
#include <stdio.h>  <br>
#include <stdlib.h> <br>

int main() { <br>
    char opt; <br>
    int n1, n2; <br>
    float res; <br>

    while (1) {
        printf("Choose an operator (+, -, *, /). Press 'x' to exit: ");
        scanf(" %c", &opt);

        if (opt == 'x') {
            exit(0);
        }



        
        printf("Enter the first number: ");
        scanf("%d", &n1);
        printf("Enter the second number: ");
        scanf("%d", &n2);

        
        switch (opt) {
            case '+':
                res = (float)n1 + n2;
                printf("Addition of %d and %d is: %.2f\n", n1, n2, res);
                break;
            case '-':
                res = (float)n1 - n2;
                printf("Subtraction of %d and %d is: %.2f\n", n1, n2, res);
                break;
            case '*':
                res = (float)n1 * n2;
                printf("Multiplication of %d and %d is: %.2f\n", n1, n2, res);
                break;
            case '/':
                if (n2 == 0) {
                    printf("Divisor cannot be zero. Please enter a non-zero divisor: ");
                    scanf("%d", &n2);
                    if (n2 == 0) {
                        printf("Still zero. Exiting to avoid division by zero.\n");
                        exit(1); // Exit if user does not provide a non-zero divisor
                    }
                }
                res = (float)n1 / n2;
                printf("Division of %d and %d is: %.2f\n", n1, n2, res);
                break;
        }
        printf("\n");
    }
}

