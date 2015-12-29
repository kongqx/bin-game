
**info frame**

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
(gdb) info frame
Stack level 0, frame at 0xbffff6c0:
 eip = 0x804840f in func (step_in.c:7); saved eip = 0x8048433
 called by frame at 0xbffff6f0
 source language c.
 Arglist at 0xbffff6b8, args: 
 Locals at 0xbffff6b8, Previous frame's sp is 0xbffff6c0
 Saved registers:
  ebp at 0xbffff6b8, eip at 0xbffff6bc
(gdb) info registers 
eax            0x1	1
ecx            0xbffff6f0	-1073744144
edx            0xbffff714	-1073744108
ebx            0xb7fc6000	-1208197120
esp            0xbffff6a8	0xbffff6a8
ebp            0xbffff6b8	0xbffff6b8
esi            0x0	0
edi            0x0	0
eip            0x804840f	0x804840f <func+20>
eflags         0x282	[ SF IF ]
cs             0x73	115
ss             0x7b	123
ds             0x7b	123
es             0x7b	123
fs             0x0	0
gs             0x33	51
```
