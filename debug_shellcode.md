
**Debug Shellcode**

```
/* ---- shellcode.c ---- */

#include <stdio.h>
#include <string.h>

unsigned char shellcode[] = "";

int main(int argc, char *argv[])
{
        printf("Shellcode Length: %d\n", strlen(shellcode));
		int (*ret)() = (int(*)())shellcode;
		ret();

		return 0;
}

// gcc -fno-stack-protector -z execstack -o shellcode shellcode.c
// gdb shellcode
```
