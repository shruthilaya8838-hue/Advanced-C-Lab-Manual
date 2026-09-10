EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:

To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```
#include <stdio.h>

int max_of_four(int a, int b, int c, int d)
{
    int greater;

    if (a >= b && a >= c && a >= d)
        greater = a;
    else if (b >= a && b >= c && b >= d)
        greater = b;
    else if (c >= a && c >= b && c >= d)
        greater = c;
    else
        greater = d;

    return greater;
}

int main()
{
    int n1, n2, n3, n4, greater;

    printf("Enter four numbers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("Greatest number = %d\n", greater);

    return 0;
}
```
Output:
```
Enter four numbers: 25 48 17 36
Greatest number = 48
```

Result:

Thus, the program  that create a function to find the greatest number is verified successfully.

 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```
#include <stdio.h>

void calculate_the_max(int n, int k)
{
    int i, j;
    int a = 0, o = 0, x = 0;
    int and_value, or_value, xor_value;

    for (i = 1; i <= n; i++)
    {
        for (j = i + 1; j <= n; j++)
        {
            and_value = i & j;
            or_value = i | j;
            xor_value = i ^ j;

            if (and_value < k && and_value > a)
                a = and_value;

            if (or_value < k && or_value > o)
                o = or_value;

            if (xor_value < k && xor_value > x)
                x = xor_value;
        }
    }

    printf("Maximum AND value = %d\n", a);
    printf("Maximum OR value = %d\n", o);
    printf("Maximum XOR value = %d\n", x);
}

int main()
{
    int n, k;

    printf("Enter n and k: ");
    scanf("%d %d", &n, &k);

    calculate_the_max(n, k);

    return 0;
}
```
Output:
```
Enter n and k: 5 4
Maximum AND value = 2
Maximum OR value = 3
Maximum XOR value = 3
```

Result:

Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.
 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```
#include <stdio.h>

int main()
{
    int noshel, noque;
    int shelarr[100][100];
    int nobookarr[100] = {0};
    int i;
    int type, shelf, book, pages;

    printf("Enter number of shelves and queries: ");
    scanf("%d %d", &noshel, &noque);

    for (i = 0; i < noque; i++)
    {
        scanf("%d", &type);

        if (type == 1)
        {
            scanf("%d %d", &shelf, &pages);

            shelarr[shelf][nobookarr[shelf]] = pages;
            nobookarr[shelf]++;
        }
        else if (type == 2)
        {
            scanf("%d %d", &shelf, &book);

            printf("%d\n", shelarr[shelf][book]);
        }
        else if (type == 3)
        {
            scanf("%d", &shelf);

            printf("%d\n", nobookarr[shelf]);
        }
    }

    return 0;
}
```
Output:
```
Enter number of shelves and queries: 5 5
1 0 15
1 0 25
1 1 30
2 0 1
3 0

25
2
```
Result:
Thus, the program to write the logic for the requests is verified successfully.

EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```
#include <stdio.h>

int main()
{
    int n, i;
    int sum = 0;

    printf("Enter the number of integers: ");
    scanf("%d", &n);

    int a[n];

    printf("Enter %d integers:\n", n);

    for (i = 0; i < n; i++)
    {
        scanf("%d", &a[i]);
        sum = sum + a[i];
    }

    printf("Sum = %d\n", sum);

    return 0;
}
```
Output:
```
 Enter the number of integers: 5
Enter 5 integers:
10
20
30
40
50
Sum = 150
```

Result:

Thus, the program prints the sum of the integers in the array is verified successfully.

EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE

Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.


Program:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char sentence[200];
    int i, count = 0;
    int inWord = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    for (i = 0; sentence[i] != '\0'; i++)
    {
        if (!isspace(sentence[i]))
        {
            if (inWord == 0)
            {
                count++;
                inWord = 1;
            }
        }
        else
        {
            inWord = 0;
        }
    }

    printf("Number of words = %d\n", count);

    return 0;
}
```
Output:
```
Enter a sentence: C programming is very interesting
Number of words = 5

```
Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
