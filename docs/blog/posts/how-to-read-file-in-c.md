---
  date: 2025-09-19
---

The following code snippet goes over how to read a file in C.

```C
#include <stdio.h>
#include <stdlib.h>

int main() {

    FILE *fptr; // 1. create an empty pointer
    fptr = fopen("input.txt", "r"); //2. use fopen(name, read access) to read a target file
    if (fptr == NULL) { // 3. check if fptr is null before proceeding
        perror ("input.txt");
        return -1; // return failure
    }

    char my_string[1024]; // 4. allocate a temporary character array of 1024 bytes
    while(fgets(my_string, 1024, fptr) != NULL) { // 5. sets the current line of 1024 bytes to my_string
        printf("%s", my_string); // 6. print
    }

    fclose(fptr); // 7. close fptr
    return 0; // 8. return 0 for success (non-zero are failures)
}
```

## Thoughts

C is a language in which you have to think in terms of the machine. You are dealing with memory, so allocating need to be precise, lengths need to be correct, null checking, and freeing memory need to be correct.
Defensive programming is important. When coming up with the solution that is very important.

The second consideration is the actual problem itself. In other languages it is easier to solve a solution to problem first, but not in C.

Which makes C a great language to get better at implementation as it forces you to become a defensive programmer when implementing a solution.