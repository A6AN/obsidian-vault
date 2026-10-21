---
tags: []
---
2025-08-26 23:10

Status: #baby 
Tags: [[C]]

# Intro to C

C is sadly a programming language. 😔

### How to write hello world in C?

`#include <stdio.h>  // Standard Input/Output header`

`int main() {`
    `printf("Hello, World!\n");  // Output text`
    `return 0;                   // End program`
`}`

### Breakdown:

- `#include <stdio.h>` → imports functions like `printf`.
    
- `int main()` → entry point. Every C program **starts** from `main()`.
    
- `{ ... }` → body of the function (where instructions live).
    
- `printf(...)` → prints text to screen.
    
- `return 0;` → tells OS program ran successfully.

Every C statement needs to be terminated using semi-colon. It indicates the end of one logical entity.
A set of logically connected statements that are surrounded by opening and closing curly braces.
### Variables and Data types

| Type     | Size (approx) | Example values      |
| -------- | ------------- | ------------------- |
| `int`    | 4 bytes       | 1, -100, 2025       |
| `float`  | 4 bytes       | 3.14, -0.5          |
| `double` | 8 bytes       | 3.141592653589      |
| `char`   | 1 byte        | 'a', 'Z', '@'       |
| `_Bool`  | 1 byte        | 0 (false), 1 (true) |
### Operators
- **Arithmetic**: `+ - * / %`
- **Relational**: `== != > < >= <=`
- **Logical**: `&& || !`
- **Increment/Decrement**: `++ --`
Identifier should start with an alphabetical character or underscore. Identifier should never have any symbol other than digit, or letter or underscore. Every identifier in C is a case sensitive string of characters.
### Input and Outputs
- Input: `scanf`
- Output: `printf`
`int num;`
`printf("Enter a number: ");`
`scanf("%d", &num);   // & = address-of`
`printf("You entered %d\n", num);`

### Conditional Statements

`if (condition) {`
    `// code`
`} else if (another condition) {`
    `// code`
`} else {`
    `// code`
`}`
#### Example
`int marks = 85;`
`if (marks >= 90) printf("Grade: A+\n");`
`else if (marks >= 75) printf("Grade: A\n");`
`else printf("Keep trying!\n");`

## Week 1 Challenges

1. Write a program that takes two numbers and prints their sum, difference, product, and quotient.
    
2. Write a program that checks if a number is **even or odd**.
    
3. Write a program that asks for your **name** and prints:
    
    `Hello, <yourname>! Welcome to C programming.`
    
4. Write a program that calculates the **area of a circle** (input radius).
    
5. Write a program that prints a **multiplication table** for a given number.

## Week 1 Answers

1. `#include <stdio.h>`

  

`int main(){`

`int num1, num2;`

`printf("Enter the first number \n");`

`scanf("%d", &num1);`

`printf("Enter the second number \n");`

`scanf("%d", &num2);`

`printf("Sum = %d\n", num1 + num2);`

`printf("Difference = %d\n", num1 - num2);`

`printf("Product = %d\n", num1 * num2);`

`printf("Qoutient = %d\n", num1 / num2);`

  

`return 0;`

`}`
    
2. `#include <stdio.h>`

  

`int main(){`

`int num;`

`printf("Enter your number \n");`

`scanf("%d", &num);`

`if (num%2 == 0)`

`{`

`printf("Number is even \n");`

`}`

`else`

`{`

`printf("Number is odd\n");`

`}`

`return 0;`

`}`
    
3. Write a program that asks for your **name** and prints:
    
    `Hello, <yourname>! Welcome to C programming.`
    
4. Write a program that calculates the **area of a circle** (input radius).
    
5. Write a program that prints a **multiplication table** for a given number.

# References

