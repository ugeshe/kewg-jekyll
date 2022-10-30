# Preprocessor

## What is it?
A preprocessor is a program that processes the source code (`.cpp, .hpp, .h`) before
compilation. It,
- Strips all the comments and replaces with a single space.
- Executes [preprocessor directives](#preprocessor-directives).

## Preprocessor directives
The lines in the code that begin with `#`. Some of them are listed below

1. `#include <...>` and `#include "..."`:
  - It replaces it with the file that it is referring to.
  - From my understanding, `<...>` are used to include non-user defined libraries and `"..."` are used to incude user defined libraries.
  - It recursively processes the inlcuded file.
2. **Conditional compilation:** The following directives are used to execute conditional compilation, `#if`, `#elif`, `#else`, and `#endif`.

```c++
#if <value>
/* code to execute if this value is true */
#elsif <value>
/* code to execute if this value is true */
#else
/* code to execut otherwise
#endif
```

3. `#define`:  Allows the programmer to give a name to a constant value before the program is compiled
6. `#undef`: Removes (undefines) a name previously created with `#define`.
4. `#ifdef`:  Compiles a section only if a specified expression has been defined with `#define`.
5. `#ifndef`: Compiles a section only if a specified expression has not been defined.
6. `#line`: Tells the preprocessor to set the compiler's reported values for the line number and filename to a given line number and filename. _??? What is the use?_

```c++
// line_directive.cpp
#include <stdio.h>

int main()
{
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
#line 10
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
#line 20 "hello.cpp"
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
    printf( "This code is on line %d, in file %s\n", __LINE__, __FILE__ );
}
```

8. `#error`: Emits a user-specified error message at compile time, and then terminates the compilation.
9. `#pragma`: Pragma directives specify machine-specific or operating system-specific compiler features. A line that starts with #pragma specifies a pragma directive. There is more to this directive which will not be explored unless used.