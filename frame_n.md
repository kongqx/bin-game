
**Demo Code**

```
#include <stdio.h>

int func1(int a)
{
        return 2 * a;
}

int func2(int a)
{
        int c = 0;
        c = 2 * func1(a);
        return c;
}

int func3(int a)
{
        int c = 0;
        c = 2 * func2(a);
        return c;
}

int main(void)
{
        printf("%d\n", func3(10));
        return 0;
}

```

Compile and run it,

```
root@lab:~/gdb-pieces# gdb frame 
Reading symbols from frame...done.
(gdb) list 
15	int func3(int a)
16	{
17	        int c = 0;
18	        c = 2 * func2(a);
19	        return c;
20	}
21	
22	int main(void)
23	{
24	        printf("%d\n", func3(10));
(gdb) break 5
Breakpoint 1 at 0x80483fe: file frame.c, line 5.
(gdb) run 
Starting program: /root/gdb-pieces/frame 

Breakpoint 1, func1 (a=10) at frame.c:5
5	        return 2 * a;
```

**frame n**

```
(gdb) bt
#0  func1 (a=10) at frame.c:5
#1  0x0804841a in func2 (a=10) at frame.c:11
#2  0x0804843c in func3 (a=10) at frame.c:18
#3  0x08048461 in main () at frame.c:24
(gdb) frame 1
#1  0x0804841a in func2 (a=10) at frame.c:11
11	        c = 2 * func1(a);
(gdb) frame 2
#2  0x0804843c in func3 (a=10) at frame.c:18
18	        c = 2 * func2(a);
(gdb) info frame
Stack level 2, frame at 0xbffff6cc:
 eip = 0x804843c in func3 (frame.c:18); saved eip = 0x8048461
 called by frame at 0xbffff6f0, caller of frame at 0xbffff6b0
 source language c.
 Arglist at 0xbffff6c4, args: a=10
 Locals at 0xbffff6c4, Previous frame's sp is 0xbffff6cc
 Saved registers:
  ebp at 0xbffff6c4, eip at 0xbffff6c8
(gdb) 

```

**up n / down n**

```
root@lab:~/gdb-pieces# gdb frame 
Reading symbols from frame...done.
(gdb) break 5
Breakpoint 1 at 0x80483fe: file frame.c, line 5.
(gdb) r
Starting program: /root/gdb-pieces/frame 

Breakpoint 1, func1 (a=10) at frame.c:5
5	        return 2 * a;
(gdb) bt
#0  func1 (a=10) at frame.c:5
#1  0x0804841a in func2 (a=10) at frame.c:11
#2  0x0804843c in func3 (a=10) at frame.c:18
#3  0x08048461 in main () at frame.c:24
(gdb) frame 2
#2  0x0804843c in func3 (a=10) at frame.c:18
18	        c = 2 * func2(a);
(gdb) up 1
#3  0x08048461 in main () at frame.c:24
24	        printf("%d\n", func3(10));
(gdb) down 2
#1  0x0804841a in func2 (a=10) at frame.c:11
11	        c = 2 * func1(a);
```
