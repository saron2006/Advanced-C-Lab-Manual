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

```
#include <stdio.h>

int main() {
    int n;
    printf("Enter a number (1 to 13): ");
    scanf("%d", &n);
    if (n < 1 || n > 13) {
        printf("Greater than 13\n");
    } else {
        switch(n) {
            case 1: 
                printf("seventy one\n");
                break;
            case 2: 
                printf("seventy two\n");
                break;
            case 3: 
                printf("seventy three\n");
                break;
            case 4: 
                printf("seventy four\n");
                break;
            case 5: 
                printf("seventy five\n");
                break;
            case 6: 
                printf("seventy six\n");
                break;
            case 7: 
                printf("seventy seven\n");
                break;
            case 8: 
                printf("seventy eight\n");
                break;
            case 9: 
                printf("seventy nine\n");
                break;
            case 10: 
                printf("eighty one\n");
                break;
            case 11: 
                printf("eighty two\n");
                break;
            case 12: 
                printf("eighty three\n");
                break;
            case 13: 
                printf("eighty four\n");
                break;
            default: 
                break;
        }
    }

    return 0;
}
```

## Output:

![Screenshot 2025-04-25 142215](https://github.com/user-attachments/assets/aff1d79d-3c74-4dce-b27d-8ca66961548e)



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

```
#include <stdio.h>

int main() {
    char a[50];
    
    printf("Enter a string: ");
    fgets(a, sizeof(a), stdin);
        int count[4] = {0, 0, 0, 0};
    
    for(int i = 0; a[i] != '\0'; i++) {
        if(a[i] >= '0' && a[i] <= '3') {
            count[a[i] - '0']++;
        }
    }
    
    for(int i = 0; i < 4; i++) {
        printf("%d ", count[i]);
    }
    
    return 0;
}
```


## Output:


![Screenshot 2025-04-25 142417](https://github.com/user-attachments/assets/36ea9c6c-2c18-448c-8577-97eb058bd17b)


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

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int compare(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

void permute(char *s[], int l, int r) {
    if (l == r) {
        for (int i = 0; i < r; i++) {
            printf("%s ", s[i]);
        }
        printf("\n");
    } else {
        for (int i = l; i < r; i++) {
            char *temp = s[l];
            s[l] = s[i];
            s[i] = temp;
                        permute(s, l + 1, r);
                        temp = s[l];
            s[l] = s[i];
            s[i] = temp;
        }
    }
}

int main() {
    int n;
    
    printf("Enter the number of strings: ");
    scanf("%d", &n);
        char **s = (char **)malloc(n * sizeof(char *));
    
    printf("Enter the strings:\n");
    for (int i = 0; i < n; i++) {
        s[i] = (char *)malloc(100 * sizeof(char)); 
        scanf("%s", s[i]);
    }
        qsort(s, n, sizeof(char *), compare);
        printf("Permutations in lexicographical order:\n");
    permute(s, 0, n);
        for (int i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);
    
    return 0;
}
```


## Output:

![Screenshot 2025-04-25 142722](https://github.com/user-attachments/assets/443c79a5-79b0-451e-9533-7600c576d812)



## Result:

Thus, the program is verified successfully
 
# EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW.

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

```
#include <stdio.h>

int main() {
    int n;
    printf("Enter the value of n: ");
    scanf("%d", &n);

    int len = n * 2 - 1;

    for (int i = 0; i < len; i++) {
        for (int j = 0; j < len; j++) {
            int top = i;
            int left = j;
            int bottom = len - 1 - i;
            int right = len - 1 - j;

            int min = top;
            if (left < min) min = left;
            if (bottom < min) min = bottom;
            if (right < min) min = right;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```

## Output:


![Screenshot 2025-04-25 142842](https://github.com/user-attachments/assets/8824ebc3-3963-461f-8fd1-b5a9bfdc6f9a)




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

```
#include <stdio.h>
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result;
    result = square();  
    printf("Square of the number is: %d\n", result);
    return 0;
}
```


## Output:


![Screenshot 2025-04-25 142954](https://github.com/user-attachments/assets/d10ef1c3-6410-4bc9-baba-ec7466ff5415)



## Result:

Thus, the program is verified successfully



























