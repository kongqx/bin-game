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
(gdb) b 5
Breakpoint 1 at 0x8048401: file step_in.c, line 5.
(gdb) b 6
Breakpoint 2 at 0x8048408: file step_in.c, line 6.
(gdb) b 7
Breakpoint 3 at 0x804840f: file step_in.c, line 7.
(gdb) save breakpoints /root/breakpoints
Saved to file '/root/breakpoints'.
(gdb) quit 
```

Save breakpoints with command ```save```.

```
root@lab:~/gdb-pieces# gdb step_in 
Reading symbols from step_in...done.
(gdb) info breakpoints 
No breakpoints or watchpoints.
(gdb) source /root/breakpoints 
Breakpoint 1 at 0x8048401: file step_in.c, line 5.
Breakpoint 2 at 0x8048408: file step_in.c, line 6.
Breakpoint 3 at 0x804840f: file step_in.c, line 7.
(gdb) info breakpoints 
Num     Type           Disp Enb Address    What
1       breakpoint     keep y   0x08048401 in func at step_in.c:5
2       breakpoint     keep y   0x08048408 in func at step_in.c:6
3       breakpoint     keep y   0x0804840f in func at step_in.c:7
```

reload gdb breakpoints with command ```source```.
