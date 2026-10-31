# C Programming Labs 01–20

Compile any program with: `gcc file.c -o out` then run `./out`

---

## Lab 01 – Basic C Programming

**1.1 Hello, World!**
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

**1.2 Name, ID, department, university**
```c
#include <stdio.h>

int main() {
    printf("Name       : Your Name\n");
    printf("ID         : 12345\n");
    printf("Department : Computer Science\n");
    printf("University : Your University\n");
    return 0;
}
```

---

## Lab 02 – Variables, Constants and Data Types

**2.1 Variables of different types**
```c
#include <stdio.h>

int main() {
    int age = 20;
    float gpa = 3.75f;
    double pi = 3.141592653;
    char grade = 'A';
    const int MAX = 100;

    printf("int    : %d\n", age);
    printf("float  : %.2f\n", gpa);
    printf("double : %.9lf\n", pi);
    printf("char   : %c\n", grade);
    printf("const  : %d\n", MAX);
    return 0;
}
```

**2.2 sizeof()**
```c
#include <stdio.h>

int main() {
    printf("char        : %zu bytes\n", sizeof(char));
    printf("short       : %zu bytes\n", sizeof(short));
    printf("int         : %zu bytes\n", sizeof(int));
    printf("long        : %zu bytes\n", sizeof(long));
    printf("long long   : %zu bytes\n", sizeof(long long));
    printf("float       : %zu bytes\n", sizeof(float));
    printf("double      : %zu bytes\n", sizeof(double));
    printf("long double : %zu bytes\n", sizeof(long double));
    return 0;
}
```

---

## Lab 03 – Input and Output

**3.1 Two integers**
```c
#include <stdio.h>

int main() {
    int a, b;
    printf("Enter two integers: ");
    scanf("%d %d", &a, &b);
    printf("First = %d, Second = %d\n", a, b);
    return 0;
}
```

**3.2 Character and string**
```c
#include <stdio.h>

int main() {
    char ch, str[100];
    printf("Enter a character: ");
    scanf(" %c", &ch);
    printf("Enter a string (no spaces): ");
    scanf("%99s", str);
    printf("Character: %c\nString: %s\n", ch, str);
    return 0;
}
```

---

## Lab 04 – Arithmetic Operators

**4.1 Basic operations**
```c
#include <stdio.h>

int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    printf("Sum        = %d\n", a + b);
    printf("Difference = %d\n", a - b);
    printf("Product    = %d\n", a * b);
    if (b != 0) {
        printf("Quotient   = %.2f\n", (float)a / b);
        printf("Remainder  = %d\n", a % b);
    } else {
        printf("Division and modulus by zero are not allowed.\n");
    }
    return 0;
}
```

**4.2 Sum and average of three numbers**
```c
#include <stdio.h>

int main() {
    float a, b, c, sum, avg;
    printf("Enter three numbers: ");
    scanf("%f %f %f", &a, &b, &c);
    sum = a + b + c;
    avg = sum / 3;
    printf("Sum = %.2f\nAverage = %.2f\n", sum, avg);
    return 0;
}
```

---

## Lab 05 – More Arithmetic Problems

**5.1 Area and circumference of a circle**
```c
#include <stdio.h>
#define PI 3.14159

int main() {
    float r;
    printf("Enter radius: ");
    scanf("%f", &r);
    printf("Area          = %.2f\n", PI * r * r);
    printf("Circumference = %.2f\n", 2 * PI * r);
    return 0;
}
```

**5.2 Celsius to Fahrenheit**
```c
#include <stdio.h>

int main() {
    float c, f;
    printf("Enter temperature in Celsius: ");
    scanf("%f", &c);
    f = (c * 9 / 5) + 32;
    printf("%.2f C = %.2f F\n", c, f);
    return 0;
}
```

---

## Lab 06 – Increment, Decrement and Assignment Operators

**6.1 Increment / decrement**
```c
#include <stdio.h>

int main() {
    int a = 5, b;

    printf("Initial a = %d\n", a);
    b = a++;
    printf("Post-increment: b = %d, a = %d\n", b, a);
    b = ++a;
    printf("Pre-increment : b = %d, a = %d\n", b, a);
    b = a--;
    printf("Post-decrement: b = %d, a = %d\n", b, a);
    b = --a;
    printf("Pre-decrement : b = %d, a = %d\n", b, a);

    a += 10; printf("a += 10 -> %d\n", a);
    a -= 3;  printf("a -= 3  -> %d\n", a);
    a *= 2;  printf("a *= 2  -> %d\n", a);
    return 0;
}
```

**6.2 Swap using a third variable**
```c
#include <stdio.h>

int main() {
    int a, b, temp;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    printf("Before swap: a = %d, b = %d\n", a, b);
    temp = a;
    a = b;
    b = temp;
    printf("After swap : a = %d, b = %d\n", a, b);
    return 0;
}
```

---

## Lab 07 – Conditional Operator

**7.1 Larger of two numbers**
```c
#include <stdio.h>

int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    int larger = (a > b) ? a : b;
    printf("Larger number = %d\n", larger);
    return 0;
}
```

**7.2 Even or odd**
```c
#include <stdio.h>

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    (n % 2 == 0) ? printf("%d is even\n", n) : printf("%d is odd\n", n);
    return 0;
}
```

---

## Lab 08 – Relational and Logical Operators

**8.1 Logical AND, OR, NOT**
```c
#include <stdio.h>

int main() {
    int a = 10, b = 20, c = 30;

    printf("(a < b) && (b < c) = %d\n", (a < b) && (b < c));
    printf("(a > b) || (b < c) = %d\n", (a > b) || (b < c));
    printf("!(a > b)           = %d\n", !(a > b));
    printf("(a > b) && (b < c) = %d\n", (a > b) && (b < c));
    return 0;
}
```

**8.2 Voting eligibility**
```c
#include <stdio.h>

int main() {
    int age;
    printf("Enter your age: ");
    scanf("%d", &age);
    if (age >= 18)
        printf("You are eligible to vote.\n");
    else
        printf("You are not eligible to vote.\n");
    return 0;
}
```

---

## Lab 09 – if Statement

**9.1 Positive, negative or zero**
```c
#include <stdio.h>

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    if (n > 0) printf("Positive\n");
    if (n < 0) printf("Negative\n");
    if (n == 0) printf("Zero\n");
    return 0;
}
```

**9.2 Even or odd**
```c
#include <stdio.h>

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    if (n % 2 == 0) printf("Even\n");
    if (n % 2 != 0) printf("Odd\n");
    return 0;
}
```

---

## Lab 10 – if-else Statement

**10.1 Leap year**
```c
#include <stdio.h>

int main() {
    int year;
    printf("Enter a year: ");
    scanf("%d", &year);
    if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0))
        printf("%d is a leap year.\n", year);
    else
        printf("%d is not a leap year.\n", year);
    return 0;
}
```

**10.2 Vowel or consonant**
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch;
    printf("Enter a character: ");
    scanf(" %c", &ch);

    if (!isalpha(ch)) {
        printf("Not an alphabet.\n");
    } else {
        char lower = tolower(ch);
        if (lower == 'a' || lower == 'e' || lower == 'i' ||
            lower == 'o' || lower == 'u')
            printf("%c is a vowel.\n", ch);
        else
            printf("%c is a consonant.\n", ch);
    }
    return 0;
}
```

---

## Lab 11 – Nested if

**11.1 Largest of three**
```c
#include <stdio.h>

int main() {
    int a, b, c;
    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    if (a >= b) {
        if (a >= c)
            printf("Largest = %d\n", a);
        else
            printf("Largest = %d\n", c);
    } else {
        if (b >= c)
            printf("Largest = %d\n", b);
        else
            printf("Largest = %d\n", c);
    }
    return 0;
}
```

**11.2 Smallest of three**
```c
#include <stdio.h>

int main() {
    int a, b, c;
    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    if (a <= b) {
        if (a <= c)
            printf("Smallest = %d\n", a);
        else
            printf("Smallest = %d\n", c);
    } else {
        if (b <= c)
            printf("Smallest = %d\n", b);
        else
            printf("Smallest = %d\n", c);
    }
    return 0;
}
```

---

## Lab 12 – else-if Ladder

**12.1 Positive, negative or zero**
```c
#include <stdio.h>

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    if (n > 0)
        printf("Positive\n");
    else if (n < 0)
        printf("Negative\n");
    else
        printf("Zero\n");
    return 0;
}
```

**12.2 Day of the week (1–7)**
```c
#include <stdio.h>

int main() {
    int d;
    printf("Enter a number (1-7): ");
    scanf("%d", &d);

    if (d == 1) printf("Monday\n");
    else if (d == 2) printf("Tuesday\n");
    else if (d == 3) printf("Wednesday\n");
    else if (d == 4) printf("Thursday\n");
    else if (d == 5) printf("Friday\n");
    else if (d == 6) printf("Saturday\n");
    else if (d == 7) printf("Sunday\n");
    else printf("Invalid input! Enter 1 to 7.\n");
    return 0;
}
```

---

## Lab 13 – switch Statement

**13.1 Arithmetic operations**
```c
#include <stdio.h>

int main() {
    float a, b;
    char op;
    printf("Enter expression (e.g. 5 + 3): ");
    scanf("%f %c %f", &a, &op, &b);

    switch (op) {
        case '+': printf("Result = %.2f\n", a + b); break;
        case '-': printf("Result = %.2f\n", a - b); break;
        case '*': printf("Result = %.2f\n", a * b); break;
        case '/':
            if (b != 0) printf("Result = %.2f\n", a / b);
            else printf("Cannot divide by zero.\n");
            break;
        default: printf("Invalid operator.\n");
    }
    return 0;
}
```

**13.2 Day of the week**
```c
#include <stdio.h>

int main() {
    int d;
    printf("Enter a number (1-7): ");
    scanf("%d", &d);

    switch (d) {
        case 1: printf("Monday\n"); break;
        case 2: printf("Tuesday\n"); break;
        case 3: printf("Wednesday\n"); break;
        case 4: printf("Thursday\n"); break;
        case 5: printf("Friday\n"); break;
        case 6: printf("Saturday\n"); break;
        case 7: printf("Sunday\n"); break;
        default: printf("Invalid input! Enter 1 to 7.\n");
    }
    return 0;
}
```

---

## Lab 14 – Loops

**14.1 Numbers 1 to 100**
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 100; i++)
        printf("%d ", i);
    printf("\n");
    return 0;
}
```

**14.2 Even numbers 1 to 100**
```c
#include <stdio.h>

int main() {
    for (int i = 2; i <= 100; i += 2)
        printf("%d ", i);
    printf("\n");
    return 0;
}
```

---

## Lab 15 – for Loop Problems

**15.1 Sum of first N natural numbers**
```c
#include <stdio.h>

int main() {
    int n, sum = 0;
    printf("Enter N: ");
    scanf("%d", &n);
    for (int i = 1; i <= n; i++)
        sum += i;
    printf("Sum = %d\n", sum);
    return 0;
}
```

**15.2 Factorial**
```c
#include <stdio.h>

int main() {
    int n;
    unsigned long long fact = 1;
    printf("Enter a number: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Factorial of a negative number doesn't exist.\n");
    } else {
        for (int i = 1; i <= n; i++)
            fact *= i;
        printf("%d! = %llu\n", n, fact);
    }
    return 0;
}
```

---

## Lab 16 – while and do-while

**16.1 Reverse digits (while)**
```c
#include <stdio.h>

int main() {
    int n, rev = 0;
    printf("Enter an integer: ");
    scanf("%d", &n);
    while (n != 0) {
        rev = rev * 10 + n % 10;
        n /= 10;
    }
    printf("Reversed = %d\n", rev);
    return 0;
}
```

**16.2 Sum of digits (do-while)**
```c
#include <stdio.h>

int main() {
    int n, sum = 0;
    printf("Enter a number: ");
    scanf("%d", &n);
    if (n < 0) n = -n;
    do {
        sum += n % 10;
        n /= 10;
    } while (n > 0);
    printf("Sum of digits = %d\n", sum);
    return 0;
}
```

---

## Lab 17 – Number Problems

**17.1 Prime check**
```c
#include <stdio.h>

int main() {
    int n, isPrime = 1;
    printf("Enter a number: ");
    scanf("%d", &n);

    if (n < 2) isPrime = 0;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) {
            isPrime = 0;
            break;
        }
    }
    if (isPrime) printf("%d is a prime number.\n", n);
    else printf("%d is not a prime number.\n", n);
    return 0;
}
```

**17.2 Primes between two numbers**
```c
#include <stdio.h>

int main() {
    int a, b;
    printf("Enter two numbers (start end): ");
    scanf("%d %d", &a, &b);

    printf("Prime numbers between %d and %d:\n", a, b);
    for (int n = a; n <= b; n++) {
        if (n < 2) continue;
        int isPrime = 1;
        for (int i = 2; i * i <= n; i++) {
            if (n % i == 0) {
                isPrime = 0;
                break;
            }
        }
        if (isPrime) printf("%d ", n);
    }
    printf("\n");
    return 0;
}
```

---

## Lab 18 – Number Series

**18.1 Fibonacci up to N terms**
```c
#include <stdio.h>

int main() {
    int n;
    long long a = 0, b = 1, next;
    printf("Enter number of terms: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        printf("%lld ", a);
        next = a + b;
        a = b;
        b = next;
    }
    printf("\n");
    return 0;
}
```

**18.2 GCD**
```c
#include <stdio.h>

int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    int x = a, y = b;
    while (y != 0) {
        int t = y;
        y = x % y;
        x = t;
    }
    printf("GCD of %d and %d = %d\n", a, b, x);
    return 0;
}
```

---

## Lab 19 – Nested Loops

**19.1 Right-angled star pattern**
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 5; i++) {
        for (int j = 1; j <= i; j++)
            printf("* ");
        printf("\n");
    }
    return 0;
}
```

**19.2 Square star pattern**
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 5; i++) {
        for (int j = 1; j <= 5; j++)
            printf("* ");
        printf("\n");
    }
    return 0;
}
```

---

## Lab 20 – Arrays

**20.1 Input and display a 1-D array (up to 10 elements)**
```c
#include <stdio.h>

int main() {
    int arr[10], n;
    printf("How many elements (1-10)? ");
    scanf("%d", &n);

    if (n < 1 || n > 10) {
        printf("Please enter a number between 1 and 10.\n");
        return 1;
    }

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &arr[i]);
    }

    printf("Array elements: ");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);
    printf("\n");
    return 0;
}
```

**20.2 Sum and average of array elements**
```c
#include <stdio.h>

int main() {
    int n;
    printf("How many elements? ");
    scanf("%d", &n);

    int arr[n];
    int sum = 0;
    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &arr[i]);
        sum += arr[i];
    }

    printf("Sum     = %d\n", sum);
    printf("Average = %.2f\n", (float)sum / n);
    return 0;
}
```
