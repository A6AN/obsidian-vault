---
tags: [machine-learning, programming]
---

2024-10-18 14:47

Status: #baby 

Tags: [[Programming]] [[R]] [[Data 104]]

# Basics to R

Basic Structure includes 
Console - where program is written
Environment - where variables and data frames are mentioned
Terminal


R is a sophisticated fancy calculator
-> To add two numbers u just add them for e.g. 5+6 then hit cmd+enter to compile it

->To assign a number to a variable u use the syntax `variable name <- number e.g.      `a <- 5`

-> To add two variables you can simply do `a+b` or `sum(a,b)` both return the same value

-> Further you can create vector are ordered collections of elements of the same data type. They can contain elements of any data type, such as numbers, characters, or logical values.

-> To create a vector you use the syntax: `vector name <- c("a","b","c...")` for e.g. `name <- c("Greg, "Paul", "Kim")` 
`age <- c(55, 45, 38)`
`logical_vector <- c(TRUE, FALSE, TRUE)`

-> You can access individual elements of a vector using their index (position). The first element has an index of 1. For example: `first_element <- numeric_vector[1]
`second_element <- character_vector[2]`

-> R provides various operations for vectors, such as:

- **Arithmetic operations:** Addition, subtraction, multiplication, division, and exponentiation.
- **Logical operations:** Comparison operators (e.g., `==`, `!=`, `<`, `>`, `<=`, `>=`) and logical operators (e.g., `&`, `|`, `!`).
- **Indexing:** Selecting specific elements or subsets of a vector.
- **Length:** Determining the number of elements in a vector.
- **Concatenation:** Combining two or more vectors.

-> R automatically recycles shorter vectors to match the length of the longer vector in arithmetic and logical operations. For example: ```
vector1 <- c(1, 2, 3)
vector2 <- c(4, 5)
result <- vector1 + vector2 # Result: 5 7 8

-> R offers numerous functions for working with vectors, including:

- **`length()`:** Returns the length of a vector.
- **`sum()`:** Calculates the sum of elements.
- **`mean()`:** Computes the average of elements.
- **`median()`:** Finds the median value.
- **`sort()`:** Sorts elements in ascending or descending order.
- **`rev()`:** Reverses the order of elements.
- **`unique()`:** Returns unique elements.

-> **A vector in R can only contain elements of the same data type.** This is a fundamental characteristic of vectors.

If you attempt to create a vector with elements of different data types, R will coerce all the elements to a common data type. For example, if you combine a numeric value with a character string, all elements will be converted to character strings.

-> Data frames combine two or more vectors into a single data frame which can be displayed as a table it can combine any type of vectors for example if we combine  
`name <- c("Alice", "Bob", "Charlie") 
`age <- c(25, 30, 28)
`gender <- c("Female", "Male", "Male")`
into a data frame we will use the syntax
`Data frame name <- data.frame(vector 1, vector 2, vector 3...)`
for example 
`friends <- data.frame(name, age, gender)`
Then the data frame "friends" will look like this:
 ``  name      age       gender
`1  Alice     25         Female 
`2  Bob       30         Male 
`3  Charlie   28          Male`

  # Opening a CSV file
  To open a csv file you need to run the command `read.csv("File_name.csv)`
  using this command you can open various file types including excel and html
  
#### Installing packages
packages are a very important part of R studios using packages can make your life easier. To install packages one must use the command. `install.packages("package_name")`



# References

