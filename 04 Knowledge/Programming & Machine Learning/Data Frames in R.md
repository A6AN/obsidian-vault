---
tags: [machine-learning, programming, r]
---

  2024-10-18 15:35

Status: #baby 

Tags: [[Programming]] [[R]] [[Vectors R]] [[Data 104]]

# Data Frames in R

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

-> Accessing Data:

- **Column Access:** Use the `$` operator or the `[]` operator with column names:
`friends$name
`friends[, "name"]`
output: 
`[1] "Alice"   "Bob"     "Charlie"`

- **Row Access:** Use the `[]` operator with row indices:
`friends[1, ]`   # First row 
`friends[c(1, 3), ]`   # Rows 1 and 3

Output:
`. name age gender
`1 Alice 25 Female
 ` name age gender
`1 Alice 25 Female 
`3 Charlie 28 Male

   -  **Specific Cell:** Access a specific cell using both row and column indices
   `friends[2, "age"]
Output:
`[1] 30`
 - **Add or remove columns:
 `friends$city <- c("New York", "Los Angeles", "Chicago")
 `friends <- friends[, -2] # Remove the second column`
 Output:
    `name gender city`
`1 Alice Female New York`
`2 Bob Male Los Angeles`
`3 Charlie Male Chicago`

     `name gender`
    `1 Alice Female`
    `2 Bob Male`
    `3 Charlie Male`



- **Add or remove rows:
`new_friend <- data.frame(name = "David", age = 27, gender = "Male")
`friends <- rbind(friends, new_friend)

Output:
    `name gender city
`1 Alice Female New York 
`2 Bob Male Los Angeles 
`3 Charlie Male Chicago 
`4 David Male <NA>
# References
