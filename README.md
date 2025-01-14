# ft_printf

## Overview

The **ft_printf** project is a custom implementation of the standard C library's `printf` function. This project was completed as part of the 42 curriculum, aiming to deepen understanding of variadic functions, formatted output, and memory management in C. The final implementation adheres to strict coding standards and replicates key features of `printf`, while introducing enhanced control and flexibility.

## Features

- Supports the following conversion specifiers:
  - **s**: String
  - **S**: Wide string (if applicable)
  - **p**: Pointer
  - **d/D**: Decimal integer
  - **i**: Integer
  - **o/O**: Octal
  - **u/U**: Unsigned integer
  - **x/X**: Hexadecimal (lowercase/uppercase)
  - **c/C**: Character
  - **%%**: Percent sign
- Handles flags: `#`, `0`, `-`, `+`, and space.
- Supports minimum field width, precision, and length modifiers (`hh`, `h`, `l`, `ll`, `j`, `z`).

## Requirements

- Adheres to the **42 Norm**.
- Handles all errors gracefully, avoiding unexpected crashes (e.g., segmentation faults, bus errors, double free issues).
- Includes a `Makefile` for compiling the library into `libftprintf.a`.

## Usage

### Compilation

To compile the library, run:
```bash
make
```
This will produce the `libftprintf.a` library file.

### Integration

To use `ft_printf` in your projects, include the header file and link the library:
```c
#include "ft_printf.h"
```
Compile your program with the library:
```bash
gcc -Wall -Wextra -Werror your_program.c -L. -lftprintf -o your_program
```

### Example

```c
#include "ft_printf.h"

int main() {
    ft_printf("Hello, %s! You have %d new messages.\n", "User", 42);
    return 0;
}
```

### Output:
```
Hello, User! You have 42 new messages.
```

## Project Details

- **Functions used:**
  - `write`
  - `malloc`
  - `free`
  - `exit`
  - Variadic argument functions (`stdarg` library)
- **Buffer Management:**
  - No custom buffer management is implemented.

## Files

- `ft_printf.c`: Core implementation of the `ft_printf` function.
- `format_handlers.c`: Contains handlers for various format specifiers.
- `utils.c`: Helper functions for string manipulation, memory management, etc.
- `Makefile`: Automates the compilation process.
- `ft_printf.h`: Header file with function prototypes and macros.
