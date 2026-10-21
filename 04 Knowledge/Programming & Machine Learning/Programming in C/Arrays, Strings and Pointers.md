---
tags: [machine-learning, programming]
---

2025-11-07 13:00

Status: #Teen 

Tags: [[C]] [[6 - Main Notes/Programming in C/Intro to C|Intro to C]]

# Arrays, Strings and Pointers

## 📚 **. Arrays**

An **array** is a _collection of elements of the same type_ stored in continuous memory.

`int arr[5] = {10, 20, 30, 40, 50};`

|Index|0|1|2|3|4|
|---|---|---|---|---|---|
|Value|10|20|30|40|50|

### Access:

`printf("%d", arr[2]); // prints 30`

### Array Properties

- `arr[i]` equals `*(arr + i)`
    
- `arr` itself represents **address of first element**
    

---

## 🧵 **. Strings**

A **string** is a character array ending with a null character `'\0'`.

`char name[] = "AYAN";`

Actually stored as:  
`'A' 'Y' 'A' 'N' '\0'`

### Common String Functions (and your versions!)

|Function|Description|You built this as|
|---|---|---|
|`strlen()`|Count characters|`my_strlen()`|
|`strcpy()`|Copy one string to another|`my_strcpy()`|
|`strcmp()`|Compare strings alphabetically|`my_strcmp()`|
|`strrev()`|Reverse a string|`my_strrev()`|

---

### Example (Your Version of `my_strlen`)

`int my_strlen(char str[]) {     int len = 0;     while (str[len] != '\0')         len++;     return len; }`

---

## 🧠 **. Functions**

Functions are reusable blocks of code.

`int add(int a, int b) {     return a + b; }  int main() {     int sum = add(2, 3); }`

### Parameter Passing

|Type|Meaning|Effect|
|---|---|---|
|**Pass by Value**|Function gets a copy|Original not changed|
|**Pass by Reference**|Function gets address|Original value changes|

---

## 🔗 **. Pointers**

A **pointer** is a variable that stores an address.

`int x = 10; int *p = &x;`

|Symbol|Meaning|
|---|---|
|`&`|Address-of operator|
|`*`|Value-at (dereference) operator|

So:

`p  → address of x   *p → value stored at that address (i.e., x)`

### Example

`printf("%d", *p); // prints value of x printf("%p", p);  // prints address of x`

---

### Pointer with Functions (Swap Example)

Without pointer:

`void swap(int a, int b) { ... } // does NOT work`

With pointer:

`void swap(int *x, int *y) {     int temp = *x;     *x = *y;     *y = temp; }`

Call:

`swap(&a, &b);`

This actually swaps the values.

---

## 🧮 **. Pointers and Arrays**

`int arr[3] = {2, 4, 6}; int *p = arr;`

|Expression|Meaning|Value|
|---|---|---|
|`arr`|address of first element|`&arr[0]`|
|`*arr`|value of first element|2|
|`*(arr+1)`|value of 2nd element|4|
|`p[2]`|same as `*(p+2)`|6|

Pointers and arrays are deeply connected.

---

# ✨ Mini Summary of Everything So Far

- **C is close to the machine**: you control memory directly.
    
- **Arrays** store multiple values of same type.
    
- **Strings** are arrays of characters ending with `'\0'`.
    
- **Functions** organize code logically.
    
- **Pointers** allow direct memory access.
    
- **Passing addresses** enables real modification of variables inside functions.




# References

