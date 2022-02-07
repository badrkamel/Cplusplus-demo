## Pointers

A pointer is a value that designates the address (i.e., the location in memory), of some value. Pointers are variables that hold a memory location.

There are four fundamental things you need to know about pointers:

How to declare them (with the address operator '&': int *pointer = &variable;)
How to assign to them (pointer = NULL;)
How to reference the value to which the pointer points (known as dereferencing, by using the dereferencing operator '*': value = *pointer;)
How they relate to arrays (the vast majority of arrays in C are simple lists, also called "1 dimensional arrays", but we will briefly cover multi-dimensional arrays with some pointers in a later chapter).
Pointers can reference any data type, even functions. We'll also discuss the relationship of pointers with text strings and the more advanced concept of function pointers.

```cpp
#include <iostream>

struct MyStruct {
    int   m_aNumber;
    float num2;
};

int main () {

	int  c, d;
	int  *pj;

	c   = 10;
	pj  = &c;             /* pj points to c */
	d   = *pj;            /* d is assigned the value to which pj points, 10 */
	pj  = &d;             /* now points to d */
	*pj = 12;             /* d is now 12 */

	// Output
	std::cout << c << std::endl;
	std::cout << d << std::endl;

	MyStruct astruct;
	MyStruct *bb;

	bb = &astruct;
	(*bb).m_aNumber = 3;  /* assigns 3 to the m_aNumber member of astruct */
	bb->num2 = 44.3;      /* assigns 44.3 to the num2 member of astruct   */
	*pj = bb->m_aNumber;  /* equivalent to d = astruct.m_aNumber;         */

	// Output
	std::cout << c << std::endl;
	std::cout << d << std::endl;

}
```

