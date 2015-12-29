
**Demo Code**

```
#include <stdio.h>

int global = 1;

int func(void) 
{
    return (++global);
}

int main(void)
{
    printf("%d\n", global);
    return 0;
}
```

**call / print**

```
root@lab:~/gdb-pieces# gdb call_print 
Reading symbols from call_print...done.
(gdb) list
3	int global = 1;
4	  
5	int func(void) 
6	{ 
7			    return (++global);
8	} 
9	  
10	int main(void)
11	{ 
12			    printf("%d\n", global);
(gdb) break 12
Breakpoint 1 at 0x8048423: file call_print.c, line 12.
(gdb) run 
Starting program: /root/gdb-pieces/call_print 

Breakpoint 1, main () at call_print.c:12
12			    printf("%d\n", global);
(gdb) call func()
$1 = 2
(gdb) print func()
$2 = 3
(gdb) quit
A debugging session is active.

	Inferior 1 [process 1028] will be killed.

	Quit anyway? (y or n) y

```

