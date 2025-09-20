---
  date: 2025-09-19
---

The following code snippet goes over how to read a file in C.

```C
#include <stdio.h>
#include <string.h>

int main() {

    FILE *fptr;
    fptr = fopen("output.txt", "w");
    if (fptr == NULL) {
        perror ("output.txt");
        return -1;
    }

    char text[1024];
    strcpy (text, "Hello, world!");
    int len = strlen(text);
    fwrite(text, sizeof(char), len, fptr); // sizeof(char) is the size of each elements in bytes. this approach is writing is general not only for text, but binary

    fclose(fptr); // 7. close fptr
    return 0; // 8. return 0 for success (non-zero are failures)
}

```
