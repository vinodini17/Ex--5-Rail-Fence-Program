# Ex--5-Rail-Fence-Program
NAME: VINODINI R


REG NO:212223040244
# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
#include <stdio.h>
#include <string.h>
int main() {
    int i, j, len, rails, count, dir;
    char str[1000];
    int code[100][1000] = {0};  // Initialize the entire array to 0
    printf("Enter a Secret Message:\n");
    scanf("%s",str);
    len = strlen(str);
    printf("Enter number of rails:\n");
    scanf("%d", &rails);
    count = 0;
    i = 0;
    dir = 1;  
    for (j = 0; j < len; j++) {
        code[i][j] = str[j];
        // Change direction if we reach the top or bottom rail
        if (i == 0) {
            dir = 1;
        } else if (i == rails - 1) {
            dir = -1;
        }
        i += dir;
    }
    printf("Encrypted Message:\n");
    // Print the encrypted message
    for (i = 0; i < rails; i++) {
        for (j = 0; j < len; j++) {
            if (code[i][j] != 0) {
                printf("%c", code[i][j]);
            }
        }
    }
    printf("\n");
    return 0;
}
```
# OUTPUT
![image](https://github.com/user-attachments/assets/e11f2f24-8f8a-4232-bf01-c05f3c8e0b53)

# RESULT
The program was executed successfully.

