
**ignore bnum count**

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
(gdb) b 12
Breakpoint 1 at 0x8048427: file step_in.c, line 12.
(gdb) ignore 1 1
Will ignore next crossing of breakpoint 1.
(gdb) run 
Starting program: /root/gdb-pieces/step_in 
3
[Inferior 1 (process 996) exited normally]
(gdb) info breakpoints 
Num     Type           Disp Enb Address    What
1       breakpoint     keep y   0x08048427 in main at step_in.c:12
	breakpoint already hit 1 time
```
