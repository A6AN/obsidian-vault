---
tags: [machine-learning, programming]
---

2024-10-18 15:15

Status: #baby 

Tags:[[Programming]] [[R]] [[Vectors R]] [[Data 104]]

# Vectors in R

-> Vector are ordered collections of elements of the same data type. They can contain elements of any data type, such as numbers, characters, or logical values.

-> To create a vector you use the syntax: `vector name <- c("a","b","c...")` for eg.           `name <- c("Greg, "Paul", "Kim")` 
`age <- c(55, 45, 38)`
`logical_vector <- c(TRUE, FALSE, TRUE)`

->  You can access individual elements of a vector using their index (position). The first element has an index of 1. For example: `first_element <- numeric_vector[1]
`second_element <- character_vector[2]`

-> R provides various operations for vectors, such as:

- **Arithmetic operations:** Addition, subtraction, multiplication, division, and exponentiation.
- **Logical operations:** Comparison operators (e.g., `==`, `!=`, `<`, `>`, `<=`, `>=`) and logical operators (e.g., `&`, `|`, `!`).
- **Indexing:** Selecting specific elements or subsets of a vector.
-  **Length:** Determining the number of elements in a vector.
- **Concatenation:** Combining two or more vectors.

->  R automatically recycles shorter vectors to match the length of the longer vector in arithmetic and logical operations. For example:  ```
vector1 <- c(1, 2, 3)
vector2 <- c(4, 5)
result <- vector1 + vector2  # Result: 5 7 8

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



# References

