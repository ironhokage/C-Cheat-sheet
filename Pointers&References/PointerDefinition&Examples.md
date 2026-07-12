
>[!IMPORTANT]
> By only **reading** this article you **WILL NOT** fully learn and remember the information presented here, to truly learn and retain what it is said in here, you have to **read**, then **make** a small piece of **code** that uses what you learned, **preferably without looking** at this documents information, if you are stuck, you should and are advised to look, and by **repeating** this cycle over a period of time you will truly **learn** and **understand**

## <ins>Operators Sheet</ins>

- for declaring a pointer (e.g. int* p)
- for dereferencing a pointer (int y = * p)
- for getting the address (int * p = &t) 

> [!NOTE]
> The ( * ) needs to **NOT** have any space between itself and the pointer, here i have put a space because the .md file format makes the text italic when i am writing
> Real code has the dereference operator attached to the pointer
> 

To remember more easily what * p (when used before a pointer) and what & do, remember this:
- The **Value** in you shines like a **Star** - for dereferencing (* p)
- A is for ampersand - for getting the address (&)

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

To declare a pointer we need the ( * ) sign.
<ins>Example:</ins>

- int* number
- char* character
- float* realNumber

<ins>Example:</ins>
- int x = 4 -> this means that "the variable of type int named x, has a value of 4"

- int* pX = &x -> this means that "the pointer of a integer named pX has the address of the variable of type int named x"

If we want to get the value of a pointer, not its address, but a value, we use the following syntax:

<img width="566" height="136" alt="Image" src="https://github.com/user-attachments/assets/462d47ef-0a44-4156-8a32-e47ac65492af" />

### <ins>What does dereferencing mean?</ins>

When we want to get the value(not the address) of a pointer we use the **dereference operator** which is represented by the ( * ) sign (not to be confused with the operator we use when declaring a pointer).

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
	- It doesn't point to a data type from the start, its data type is "void" meaning it has NO data type.
	- It can hold the address of any data type.
	- It must be assigned a memory address first before dereferencing, it cannot be dereferenced directly
	- To access the value, you must cast it to the correct type first ( e.g., int* pInt = (int*)voidPtr; ).

Example:

<img width="670" height="237" alt="Image" src="https://github.com/user-attachments/assets/399aad12-5f47-43ab-95f7-90bf6c174e06" />

4. <ins> Pointers to Pointers </ins>
	- In C++ we can make pointers that point to other pointers, these can point to data or other pointers.
	- To make a pointer of pointers/ to point to another pointer we just use the ( * ) symbol.

Example:

<img width="279" height="152" alt="Image" src="https://github.com/user-attachments/assets/4449dbd5-50b0-442d-93d3-4d30b3cfb4fd" />

5. <ins> Dangling Pointer </ins>
    - A pointer that points to a value that has been freed or deleted.
    - Accessing a `dangling pointer` leads to errors and undefined behavior.
    - **Example:** A `dangling pointer` is like someone giving you the address to a house, and when you go to that address you see that the house has been demolished.

6. <ins> Wild Pointer </ins>
	- A pointer of this type has not been initialized to a valid address.
	- Accessing a `wild pointer` is dangerous and error prone.
	- **Example:** Think of a `wild pointer` like a boat without a anchor, the boat is the pointer, the anchor is the memory address, without a anchor(memory address) the boat(pointer) will drift and arrive in unexpected places(the undefined behavior of a `wild pointer`)

7. <ins> Smart Pointer </ins>
	- There are 4 types (one of them is deprecated though, so we will just mention it briefly)
	1. auto_ptr (Deprecated)
		* It was an early smart pointer that automatically deleted the managed object when it wasn't needed anymore(i.e. went out of scope)
		* **Example:** When someone sells their car lets say, they give their ownership to someone else, thus, if they had copies to the car keys they need to destroy them, that's what `std::auto_ptr` was doing, when the ownership was transferred, the original pointer was null, thus not needed, thus destroyed

	2. unique_ptr
		* It is used when we want to store one, unique (as the name suggests) pointer.
		* We can only move the ownership of the object to another `std::unique_ptr`, we can NOT copy `std::unique_ptr`.
		* To move the ownership of the object we use the `std::move()` method.
		* When the `std::unique_ptr` goes out of scope(it isn't needed anymore) or is destroyed, then it automatically deletes the object it owns. This means no manual delete calls and no memory leaks.
		* It is the default choice for 90% of raw pointer use cases in modern C++ because it has zero runtime overhead compared to a raw pointer.
		* **Example:** To better understand `std::unique_ptr`, we can say that its like a piece of unique art, like the Mona Lisa, you can move owners, sell it to some one else, but you can't make a 1:1 copy of it. 
		
	3. shared_ptr
		- This type of smart pointer allows multiple pointers to share ownership of the same object between them.
		- It uses reference counting to manage how many pointers are that share the ownership on the same object.
		- **Example:** To better understand this concept is like two people share custody of a dog or any other pet, they both are the owners of said animal.
		
	4.  weak_ptr
		- This type of pointer does **NOT** own objects, it is used in combination with `std::shared_ptr` to prevent circular dependencies.
		- A circular dependency appears when two objects hold a pointer to each other.
		- If two objects hold `std::shared_ptr`, then the reference count **NEVER** reaches zero and thus memory leaks will occur.
		- This is fixed by using `std::weak_ptr`, because it doesn't own references to an object managed by `std::shared_ptr` there won't be any circular dependencies.
		- When using a `std::weak_ptr` we still have access to the object owned by `std::shared_ptr` but we don't own it, we have to first use the `.lock()` on it, which returns a `std::shared_ptr`. If the original object is valid, we get a valid object, if not we get a `nullptr`.
		- **Example:** Think of a `shared_ptr` as a **hotel room key** that keeps the room reserved. A `weak_ptr` is a **receptionist's note** that says _"Guest in Room 204"_. The note doesn't keep the room alive—if all keys are returned, housekeeping destroys the room. If you knock on the door (call `.lock()`), you either get a temporary key (valid `shared_ptr`) or find an empty room (`nullptr`)

>[!IMPORTANT]
> auto_ptr was deprecated in C++11 and removed in C++17.

8. <ins>Constant pointer</ins>
	- A pointer of this type has a fixed memory location.
	- Its value can be changed, but the memory address will still point to the same location because it is made constant here.
	- You can **NOT** change the address of this type of pointer, using the & operator will lead to errors.
	- **Example:** Its like a house that remains on the same street, and the streets name doesn't change and the only thing that changes is who stays in said house, the people are the value, and the house is the `constant pointer`.


## <ins>Sources used</ins>:
1. https://www.geeksforgeeks.org/cpp/smart-pointers-cpp/
2. https://cplusplus.com/doc/tutorial/pointers/
3. https://www.geeksforgeeks.org/cpp/difference-between-constant-pointer-pointers-to-constant-and-constant-pointers-to-constants/
4. 
