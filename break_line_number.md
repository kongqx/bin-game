
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
```


```
(gdb) b step_in.c:6
Breakpoint 2 at 0x8048408: file step_in.c, line 6.
```

If you modify lines of code, breakpoint may be different.
