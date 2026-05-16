Q: What does `#include` do in C?
A: It imports the contents of a header file (library) into your program.

Q: What does `<unistd.h>` stand for?
A: UNIX Standard Header.

Q: What kind of functions does `<unistd.h>` provide?
A: System-level functions for interacting with the operating system via the POSIX API.

Q: What does POSIX stand for?
A: Portable Operating System Interface.

Q: What does `<stdio.h>` stand for?
A: Standard Input/Output.

C: `<unistd.h>` stands for [UNIX Standard Header].

C: `<stdio.h>` stands for [Standard Input/Output].

Q: What are the three arguments `write()` takes?
A: The file descriptor (where to write), the string/data, and the length of the string.

Q: Why must you pass the string length to `write()`?
A: Because detecting string length in C requires manually counting bytes, so providing it is more efficient.

Q: What file descriptor do you pass to `write()` to print to the terminal?
A: `1` (standard output / stdout).

Q: What does file descriptor `0` represent?
A: Standard Input (stdin).

Q: What does file descriptor `1` represent?
A: Standard Output (stdout).

Q: What does file descriptor `2` represent?
A: Standard Error (stderr).

C: File descriptor [0] = stdin, [1] = stdout, [2] = stderr.

Q: What is `printf()` a wrapper of?
A: The `write()` function.

Q: What does it mean for a function to be a "wrapper" of another?
A: The wrapper's primary job is to call the other function behind the scenes, hiding its manual details.

Q: What does the `f` in `printf` stand for?
A: Format — it allows you to embed different data types inside a string literal.

Q: What manual work does `printf()` handle that `write()` requires you to do yourself?
A: Counting the byte length of the string.

Q: Which header file do you include to use `printf()`?
A: `<stdio.h>`

Q: Which header file do you include to use `write()`?
A: `<unistd.h>`

C: `printf()` is imported via `#include [<stdio.h>]`.

C: `write()` is imported via `#include [<unistd.h>]`.

Q: What does it mean that C is a statically typed language?
A: The compiler checks that all operations use compatible data types at compile time, before the program runs.

Q: When does type checking happen in C?
A: During compilation (it is a static process).

Q: What must you always specify for a function in C?
A: The return type (e.g. `void`, `int`).

Q: What return type means a function returns nothing in C?
A: `void`

C: C is a [statically] typed language — types are checked at [compile] time.

C: A function that returns nothing has return type [void].

Q: What is special about `main()` in C?
A: It is the entry point of the program — where execution begins.

Q: Can you name your own functions something other than `main` in C?
A: Yes. `main` is just the name C recognises as the entry point; other functions can be named anything.

C: C treats [main()] as the entry point of a program.

Q: What should `int main()` return on success, and why?
A: `0` — a return value of 0 signals to the OS that the program exited without error. Returning 1 signals an error.

Q: What is a segmentation fault?
A: An error that occurs when your program tries to read memory it doesn't have permission to access.

Q: What is one common cause of a segmentation fault in C?
A: Using an incorrect format specifier (e.g. with `printf`).

C: A [segmentation fault] means the program tried to read memory it has no permission to access.

Q: What is casting in C?
A: Taking a piece of memory and choosing to interpret it as a different type.

Q: How is an integer like `1` stored in memory in C?
A: As a 32-bit binary value (32 ones and zeros).

Q: How is the third argument `13` in `write(1, "Hello, World!", 13)` stored in memory?
A: As a 64-bit integer.

Q: What is computer memory, at its most fundamental level in C?
A: A large global array of bytes, each at a numbered index (address).

C: In C, memory is modelled as a large [array] of [bytes].

C: Casting means taking a piece of memory and [interpreting] it as a different type.

Q: What character encodings does C use for strings?
A: ASCII, and more recently UTF-8 (Unicode).

Q: Who does the actual interpretation and display of bytes output by a C program?
A: The shell — the program hands bytes to the shell, and the shell interprets and displays them.

Q: What does C actually store when you declare a string like `"Hello, World!"`?
A: The memory address of the first byte of the string, not the characters themselves.

Q: In `write(1, "Hello, World!", 13)`, what role does the string argument play internally?
A: It is the starting memory address (index) into the byte array; `13` then tells `write` how many bytes to read from that point.

C: C stores a string as the [memory address] of its [first byte].

C: `write()`'s second argument is the [start address] of the data; its third argument is the [number of bytes] to output.

Q: What does the term "pointer" mean in C?
A: A memory address — a number that points to (indexes into) a specific location in the global array of bytes.

Q: What does the `*` symbol mean in a declaration like `char *header`?
A: It declares `header` as a pointer — it holds the memory address of a byte (a `char`), not the character itself.

Q: What is a memory address?
A: An index into the large global array of bytes that represents all of computer memory.

C: A [pointer] is a memory address — an index into the global array of bytes.

C: In `char *header`, the [*] makes `header` a pointer to a memory address rather than a direct value.

Q: What is a null terminator?
A: A zero byte (`\0`) placed at the end of a C string to mark where the string ends.

Q: Why do C strings need a null terminator?
A: Because C strings are just pointers to a start byte — without a terminator, there is no way to know where the string ends.

Q: Where did you first encounter a null terminator in the notes?
A: In an HTTP response string like `"HTTP/1.1 200 OK"` — the server appends a 0 byte to mark the end.

C: A C string ends with a [null terminator] — a [0] byte that marks the end of the string.
