This is a C++ school project that replicates a simple calculator using basic programming logic and it allows the user to perform fundamental arithmetic operations such as addition, subtraction, multiplication, and modulo. It also includes increment and decrement functionalities. 
The calculator takes user input for values and operations, then displays the result accordingly.

The code for this one 
#include<stdio.h>

int myCalc() {
    int nums[3];
    char op;
    int ans = 0, i;

    printf("\n=======================================================================\n");
    printf("\nEnter Three numbers\n");
    for (i = 0; i < 3; i++) {
        printf("Input Number %d: ", i + 1);
        scanf("%d", &nums[i]);
    }

    while (getchar() != '\n');

    printf("Enter an operator (+, -, *, /, %%, i for increment, d for decrement): ");
    scanf(" %c", &op);

    switch (op) {
        case '+':
            ans = nums[0] + nums[1] + nums[2];
            printf("\nThe result of %d, %d, and %d is %d\n", nums[0], nums[1], nums[2], ans);
            break;
        case '-':
            ans = nums[0] - nums[1] - nums[2];
            printf("\nThe result of %d, %d, and %d is %d\n", nums[0], nums[1], nums[2], ans);
            break;
        case '*':
            ans = nums[0] * nums[1] * nums[2];
            printf("\nThe result of %d, %d, and %d is %d\n", nums[0], nums[1], nums[2], ans);
            break;
        case '/':
            if (nums[1] != 0 && nums[2] != 0) {
                ans = nums[0] / nums[1] / nums[2];
                printf("\nThe result of %d, %d, and %d is %d\n", nums[0], nums[1], nums[2], ans);
            } else {
                printf("\nInvalid Divisor\n");
            }
            break;
        case '%':
            if (nums[1] != 0 && nums[2] != 0) {
                ans = nums[0] % nums[1] % nums[2];
                printf("\nThe result of %d, %d, and %d is %d\n", nums[0], nums[1], nums[2], ans);
            } else {
                printf("\nInvalid Divisor\n");
            }
            break;
        case 'i':
            printf("\nThe result of %d, %d, and %d\n", nums[0] + nums[1], nums[1] + nums[2], nums[2] + nums[0]);
            break;
        case 'd':
            printf("\nThe result of %d, %d, and %d\n", nums[0] - nums[1], nums[1] - nums[2], nums[2] - nums[0]);
            break;
        default:
            printf("\nInvalid operator\n");
    }

    return 0; // Return 0 to indicate success
}

int main() {
    char tryUle;

    do {
     
        myCalc();

        printf("\nDo you want to try again (y/n): ");
        while (getchar() != '\n');
        scanf("%c", &tryUle);

    } while (tryUle == 'y' || tryUle == 'Y');

    printf("\nThank you for using the calculator.\n");

    return 0; // Main also returns 0 to indicate successful execution
}
