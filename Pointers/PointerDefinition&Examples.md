# Pointers - Definition & Examples

## <ins>Signs Sheet</ins>

- for declaring a pointer (e.g. int* p)
- for dereferencing a pointer (int y = *p)
- for getting the address (int *p = &t)

## <ins>Types of pointers</ins>

- value pointers(char*, etc)
- null pointers
- void pointers
- pointers to pointers
- pointers to functions
- dangling pointer
- wild pointer
- smart pointer
- constant pointer
- pointer to constant
- constant pointer to constant
- "this" pointer
- nullptr

## <ins>What are pointers?</ins>

Pointers are a variable that stores the memory address of another variable.

They can store the memory address of any variable type(char, int, float, etc).

When a variable points to the address of another variable that is called a **pointer**

### <ins>What is a address?</ins>

The memory is split between address and value, the address is the location in the memory where the value lives.

For example if you have a house, its address is where on the street, or city, that house is.

### <ins>How are pointers declared?</ins>

To declare a pointer we need the (*) sign.
<ins>Example:</ins>

- int* number
- char* character
- float* realNumber

<ins>Example:</ins>
- int x = 4 -> this means that "the variable of type int named x, has a value of 4"

- int* pX = &x -> this means that "the pointer of a integer named pX has the address of the variable of type int named x"

If we want to get the value of a pointer, not its address, but a value, we use the following sintax:

- int y = *pX -> this means "the variable of type int named y has the value of the dereferenced pointer pX"

### <ins>What does dereferencing mean?</ins>

When we want to get the value(not the address) of a pointer we use the **dereference operator** which is represented by the (*) sign (not to be confused with the operator we use when declaring a pointer).

### <ins> How to obtain the memory address of a variable?</ins>

To get the memory address of a variable we have to use the (&) operator/sign.

This is used when we have a variable, lets say float PI = 3.1415f and we want to assign its memory address to a pointer lets say we have float* pPI = &PI

### <ins> Types of pointers, explinations and examples </ins>

1. <ins> Value Pointers </ins>
	- The pointer that stores a memory address of any data type.
	- It is initialized with a known data type before using and its given a value.

Example:

<img width="407" height="165" alt="Image" src="https://github.com/user-attachments/assets/db75c76f-1934-43ec-95bd-cdf7f00ae538" />

2. <ins> Null Pointers </ins>
	- A pointer that doesn't point to any valid memory address
	- It's initialized with the keyword "nullptr" or "NULL".

Example:

<img width="280" height="124" alt="Image" src="https://github.com/user-attachments/assets/e326e273-3a0a-494f-8597-0985abeb484e" />

3. <ins> Void Pointers </ins>
	- It doesn't have a valid memory address from the start.
	- It can hold the address of any data type.
	- It must be assigned a memory address first before dereferencing, it cannot be dereferenced directly

Example:

<img width="670" height="237" alt="Image" src="https://github.com/user-attachments/assets/399aad12-5f47-43ab-95f7-90bf6c174e06" />

4. <ins> Pointers to Pointers </ins>
	- In C++ we can make pointers that point to other pointers, these can point to data or other pointers.
	- To make a pointer of pointers/ to point to another pointer we just use the (*) symbol.

Example:
char a = '*';
char * b = &a;
char ** c = &b;



