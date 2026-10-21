---
tags: [machine-learning, programming]
---

2025-11-07 13:05

Status: #Teen 

Tags: [[6 - Main Notes/Programming in C/Intro to C|Intro to C]] [[C]]

# Structures

Structures are group of data types. Think of it like a template, you use a template and enter your own details into it similarly in making structures you create variables in that structure and then add details according to the data types (template) of the structure.

---

## Syntax
`Struct Student` 
`{`
`char name[50];`
`int age;`
`float marks;`
`}`
`struct student s1;`
`struct student s2;`

There are two ways to assign a value to a struct variable ->
1.
`struct student s1 = { "Ayan", 21, 95.5};`

2.
`strcpy(s1.name, "Ayan") 
`s1.age = 21;
`s1.marks = 95.5;



---


# References

