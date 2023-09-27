# Chapter 12 Pointer Lab

## CS 202 Fall 2023

**Name(s):** Jazon Valencia

**Answer the following questions.** You may work individually or with one lab partner, but only one submission is permitted and must have both names listed. Both partners will receive the same score. Submit through the Canvas drop box.

1. Each byte in memory is assigned a unique **address**.

2. The **address of (&)** operator can be used to determine a variable's address.

3. **Pointer** variables are designed to hold addresses.

4. The **indirection** operator can be used to work with the variable a pointer points to.

5. Array names can be used as **a pointer constant** and vice-versa.

6. Creating variables while a program is running is called **dynamic allocation**.

7. The **new** operator is used to dynamically allocate memory.

8. If the new operator cannot allocate the amount of memory requested, it throws **a** `bad_alloc` **exception**.

9. A pointer that contains the address 0 is called a(n) **null** pointer.

10. When a program is finished with a chunk of dynamically allocated memory, it should free it with the **delete** operator.

11. You should only use the delete operator to deallocate memory that was dynamically acquired with the **new** operator.

12. What does the indirection operator do?
**The indirection operator is used to get the value located at a memory address.**

13. Look at the following code.

    ```cpp
    int  x = 7;
    int* ptr = &x;
    ```

    What will be displayed if you send the expression `*ptr` to `cout`? What happens if you send the expression `ptr` to `cout`?
**If you send** `*ptr` **to** `cout`**, the value 7 will be output. On the other hand, if you send the expression** `ptr` **to** `cout`**, then the address of** `x` **will be output.**

14. Name two different uses for the C++ operator `*`.
**The**  `*` **operator can be used for multiplication as well as dereferencing a pointer.**
15. Which arithmetic operations can be applied to pointers?
**The** `+` **and** `-` **operators can be applied to pointers.**

16. Assuming that `ptr` is a pointer to an `int`, what happens when you add 4 to it?
**The expression** `ptr + 4` **is equivalent to moving 4 memory addresses from the base address, scaled according to** `int`.**

17. Look at the following array definition.

    ```cpp
    int numbers [] = {2, 4, 6, 8, 10};
    ```

    What will the following statement display?

    ```cpp
    cout << *(numbers + 3) << endl;
    ```
**The statement will display 6.**

18. What is the purpose of the `new` operator?
**Normally, variables allocate memory at compile time. When the program requires a new variable, the** `new` **operator can be used to create a variable _during_ the execution of the program.** 

19. What happens when a program uses the `new` operator to allocate a block of memory, but the amount of requested memory isn't available? How do programs written with older compilers handle this?
**If there is not enough memory available to allocate a block of memory, a** `bad_alloc` **exception is thrown. The exception must be handled, otherwise the program will terminate.**

20. Under what circumstances can you successfully return a pointer from a function?
**You can return a pointer from a function by declaring the return type as a pointer of a data type. For example:**
 ```cpp
 int* functionName(int* &number) {
     return number;
}
 ```

21. What is the purpose of the `delete` operator?
**The purpose of the delete operator is to destroy memory allocated when the**

22. What is the difference between a pointer to a constant and a constant pointer?
**A constant pointer cannot change values to another memory address. A constant variable cannot change values, but if a pointer is pointing to a constant variable, the value of the pointer can still change.**
23. Show C++ code for defining a variable `ptr` that is a pointer to a constant `int`.
```cpp
const int FACTOR = 2;
int* ptr = &FACTOR;
```
24. Show C++ code for defining a variable `ptr` that is a constant pointer to `int`.
```
int a = 14;
const int* ptr = &a;
```

25. The following declarations are an attempt to access the array data using subscripts that start at one. Will it work? Why or why not?

    ```cpp
    int  actual_data[20];
    int* data = actual_data - 1;
    ```
**No, this will not work because** `int* data = actual_data - 1` **is referencing out of bounds.**

26. What are the differences (if any) between the variables `array1` and `array2` in this function?

    ```cpp
    void function(int array1[10] ) {
        int array2[10];
        ...
    }
    ```
**The difference between** `array1` **and** `array2` **is that** `array1` **is being passed to the function and** `array2` **is being declared within the function.** `array1` **may be an invalid syntax because you cannot pass a whole array by value to a function.** 

27. Given the declarations and data shown below, evaluate each of the expressions and state its value. Evaluate each expression with the original data shown (that is, the results of one expression do not affect the following one). Assume that the ints array begins at location 1000 and that integers and pointers both occupy *four* bytes of memory. Note: Some expressions are undefined.

    ```cpp
    int ints[20] = { 
         10,  20,  30,  40,  50,  60,  70,  80,  90, 100,
        100, 120, 130, 140, 150, 160, 170, 180, 190, 200
    };
    int *ip = ints + 3;
    ```

    | Expression    | Value         | Expression  | Value         |
    | ------------- | ------------- | ----------- | ------------- |
    | `ints`        |  1000          | `ip`        |         1012      | 
    | `ints[4]`     |      50         | `ip[4]`     |         80   |
    | `ints + 4`    |        1016       | `ip + 4`    |      1028        |
    | `*ints + 4`   |        50       | `*ip + 4`   |      80         |
    | `*(ints + 4)` |      50         | `*(ip + 4)` |       80	        |
    | `ints[-2]`    |       undefined        | `ip[-2]`    |      20         |
    | `&ints`       |     1000          | `&ip`       |       1012        |
    | `&ints[4]`    |      1016         | `&ip[4]`    |    1028           |
    | `&ints + 4`   |        1016       | `&ip + 4`   |     1028          |
    | `&ints[-2]`   |      undefined         | `&ip[-2]`   |        1008       |

28. Recall that C++ is row-major language. Given the declaration:

    ```cpp
    int array[4][2];
    ```

    Give the value of each of the following expressions. Assume that the array begins at location 100 and that integers occupy two bytes of memory.

    | Expression     | Value         |
    | -------------- | ------------- | 
    | `array`        |      100     |
    | `array + 2`    |       104       |
    | `array[3]`     |         112     |
    | `array[2] - 1` |         106     |
    | `&array[1][2]` |       108        |
    | `&array[2][0]` |        108       |

<!--EOF-->
