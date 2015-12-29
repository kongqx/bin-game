
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
(gdb) break 7
Breakpoint 1 at 0x804840f: file step_in.c, line 7.
(gdb) run
Starting program: /root/gdb-pieces/step_in 

Breakpoint 1, func () at step_in.c:7
7			return 3;
(gdb) quit 
A debugging session is active.

	Inferior 1 [process 1239] will be killed.

	Quit anyway? (y or n) y

```

**set confirm off**

```
root@lab:~/gdb-pieces# gdb step_in 
Reading symbols from step_in...done.
(gdb) set confirm off
(gdb) break 7
Breakpoint 1 at 0x804840f: file step_in.c, line 7.
(gdb) run 
Starting program: /root/gdb-pieces/step_in 

Breakpoint 1, func () at step_in.c:7
7			return 3;
(gdb) quit 

```
