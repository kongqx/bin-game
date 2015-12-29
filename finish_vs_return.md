
Demo Code:

```
#include <stdio.h>

int func(void)
{
		int a = 0;
		int b = 1;
		return 3;
}

int main(void)
{
		int a = 0;

		a = func();
		printf("%d\n", a);
		return 0;
}

```

Set a breakpoint

```
root@lab:~/gdb-pieces# gdb step_in 
Reading symbols from step_in...done.
(gdb) list
3	int func(void)
4	{
5			int a = 0;
6			int b = 1;
7			return 3;
8	}
9	
10	int main(void)
11	{
12			int a = 0;
(gdb) break 5
Breakpoint 1 at 0x8048401: file step_in.c, line 5.
(gdb) run 
Starting program: /root/gdb-pieces/step_in 

Breakpoint 1, func () at step_in.c:5
5			int a = 0;

```

**finish**

execute the following code, and return,

```
(gdb) finish 
Run till exit from #0  func () at step_in.c:5
0x08048433 in main () at step_in.c:14
14			a = func();
Value returned is $1 = 3
```

**return**

return directly.

```
(gdb) return 
Make func return now? (y or n) y
#0  0x08048433 in main () at step_in.c:14
14			a = func();
```


