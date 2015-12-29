
Demo code:

```
#include <stdio.h>

int func(void)
{
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

compile code and debug it,

    root@lab:~/gdb-pieces# gcc -ggdb -o step_in step_in.c

At first, we need a breakpoint,

```
(gdb) disassemble main 
Dump of assembler code for function main:
   0x08048405 <+0>:	lea    0x4(%esp),%ecx
   0x08048409 <+4>:	and    $0xfffffff0,%esp
   0x0804840c <+7>:	pushl  -0x4(%ecx)
   0x0804840f <+10>:	push   %ebp
   0x08048410 <+11>:	mov    %esp,%ebp
   0x08048412 <+13>:	push   %ecx
   0x08048413 <+14>:	sub    $0x14,%esp
   0x08048416 <+17>:	movl   $0x0,-0xc(%ebp)
   0x0804841d <+24>:	call   0x80483fb <func>
   0x08048422 <+29>:	mov    %eax,-0xc(%ebp)
   0x08048425 <+32>:	sub    $0x8,%esp
   0x08048428 <+35>:	pushl  -0xc(%ebp)
   0x0804842b <+38>:	push   $0x80484e0
   0x08048430 <+43>:	call   0x80482d0 <printf@plt>
   0x08048435 <+48>:	add    $0x10,%esp
   0x08048438 <+51>:	mov    $0x0,%eax
   0x0804843d <+56>:	mov    -0x4(%ebp),%ecx
   0x08048440 <+59>:	leave  
   0x08048441 <+60>:	lea    -0x4(%ecx),%esp
   0x08048444 <+63>:	ret    
End of assembler dump.
(gdb) break *main+24
Breakpoint 2 at 0x804841d: file step_in.c, line 12.
(gdb) run 
Starting program: /root/gdb-pieces/step_in 

Breakpoint 2, main () at step_in.c:12
12			a = func();
```

**step**

step into the function,

```
(gdb) run 
Starting program: /root/gdb-pieces/step_in 

Breakpoint 2, main () at step_in.c:12
12			a = func();
(gdb) step
func () at step_in.c:5
5			return 3;
(gdb) step
6	}

```

**next**

step over the function, 

```
(gdb) run 
The program being debugged has been started already.
Start it from the beginning? (y or n) y
Starting program: /root/gdb-pieces/step_in 

Breakpoint 2, main () at step_in.c:12
12			a = func();
(gdb) next
13			printf("%d\n", a);
```
