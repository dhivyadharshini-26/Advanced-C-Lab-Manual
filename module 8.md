# EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
## Aim:
To write a C program print the lowercase English word corresponding to the number
## Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
## Program:
```c
#include <stdio.h>

int main() {
    int n;
    
    printf("Enter a number (1-9): ");
    scanf("%d", &n);
    
    switch(n) {
        case 1:
            printf("one\n");
            break;
        case 2:
            printf("two\n");
            break;
        case 3:
            printf("three\n");
            break;
        case 4:
            printf("four\n");
            break;
        case 5:
            printf("five\n");
            break;
        case 6:
            printf("six\n");
            break;
        case 7:
            printf("seven\n");
            break;
        case 8:
            printf("eight\n");
            break;
        case 9:
            printf("nine\n");
            break;
        default:
            printf("Greater than 9\n");
    }
    
    return 0;
}
```
## Output:
<img width="397" height="218" alt="image" src="https://github.com/user-attachments/assets/fe97d433-9864-442e-b890-f75da6642cdb" />

## Result:
Thus, the program is verified successfully
 
# EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
## Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
## Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
## Program:
```c
#include <stdio.h>
#include <string.h>

int main() {
    char a[50];
    int h = 0;
    int len;

    printf("Enter a string: ");
    scanf("%s", a);

    len = strlen(a);

    while (h <= 3) {
        int c = 0;
        for (int i = 0; i < len; i++) {
            if (a[i] == '0' + h) {
                c++;
            }
        }
        printf("%d ", c);
        h++;
    }
    printf("\n");

    return 0;
}
```
## Output:
<img width="427" height="202" alt="image" src="https://github.com/user-attachments/assets/ff86d8ff-ba55-4311-84e5-6b949a78c92c" />

## Result:
Thus, the program is verified successfully

# EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
## Aim:
To write a C program to print all of its permutations in strict lexicographical order.

## Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
## Program:
```c
#include <stdio.h>
#include <string.h>

int main() {
    int n;
    char str[50][50], temp[50];

    printf("Enter number of strings: ");
    scanf("%d", &n);

    printf("Enter the strings:\n");
    for (int i = 0; i < n; i++) {
        scanf("%s", str[i]);
    }

    // Sorting (Very simple bubble sort)
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (strcmp(str[i], str[j]) > 0) {
                strcpy(temp, str[i]);
                strcpy(str[i], str[j]);
                strcpy(str[j], temp);
            }
        }
    }

    printf("\nStrings in lexicographical order:\n");
    for (int i = 0; i < n; i++) {
        printf("%s ", str[i]);
    }

    return 0;
}
```
## Output:
<img width="478" height="315" alt="image" src="https://github.com/user-attachments/assets/09f0bcfb-a710-4cc1-ae41-5feb4659ab5d" />

## Result:
Thus, the program is verified successfully
 
# EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
## Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
## Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
## Program:
```c
#include <stdio.h>

int main() {
    int n;
    printf("Enter n: ");
    scanf("%d", &n);

    int len = n * 2 - 1;

    for (int i = 0; i < len; i++) {
        for (int j = 0; j < len; j++) {

            int top = i;
            int left = j;
            int right = (len - 1) - j;
            int bottom = (len - 1) - i;

            int min = top;
            if (left < min) min = left;
            if (right < min) min = right;
            if (bottom < min) min = bottom;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}

```
## Output:
<img width="402" height="331" alt="image" src="https://github.com/user-attachments/assets/c923abb3-0e2d-4fca-aabc-ccf3492f08e2" />

## Result:
Thus, the program is verified successfully

# EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

## Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

## Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

## Program:
```c
#include <stdio.h>

int square() {   // Function with no arguments, returns int
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);

    return n * n;   // return square
}

int main() {
    int result;

    result = square();   // function call

    printf("Square = %d\n", result);

    return 0;
}
```
## Output:
<img width="401" height="237" alt="image" src="https://github.com/user-attachments/assets/9b9faae1-b963-466e-a7cb-e4d9e86b240f" />

## Result:
Thus, the program is verified successfully
