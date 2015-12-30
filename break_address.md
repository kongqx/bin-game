
```
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
(gdb) disassemble main
Dump of assembler code for function main:
   0x08048416 <+0>:	lea    0x4(%esp),%ecx
   0x0804841a <+4>:	and    $0xfffffff0,%esp
   0x0804841d <+7>:	pushl  -0x4(%ecx)
   0x08048420 <+10>:	push   %ebp
   0x08048421 <+11>:	mov    %esp,%ebp
   0x08048423 <+13>:	push   %ecx
   0x08048424 <+14>:	sub    $0x14,%esp
   0x08048427 <+17>:	movl   $0x0,-0xc(%ebp)
   0x0804842e <+24>:	call   0x80483fb <func>
   0x08048433 <+29>:	mov    %eax,-0xc(%ebp)
   0x08048436 <+32>:	sub    $0x8,%esp
   0x08048439 <+35>:	pushl  -0xc(%ebp)
   0x0804843c <+38>:	push   $0x80484f0
   0x08048441 <+43>:	call   0x80482d0 <printf@plt>
   0x08048446 <+48>:	add    $0x10,%esp
   0x08048449 <+51>:	mov    $0x0,%eax
   0x0804844e <+56>:	mov    -0x4(%ebp),%ecx
   0x08048451 <+59>:	leave  
   0x08048452 <+60>:	lea    -0x4(%ecx),%esp
   0x08048455 <+63>:	ret    
End of assembler dump.
(gdb) break *0x08048441
Breakpoint 1 at 0x8048441: file step_in.c, line 15.
(gdb) info breakpoints 
Num     Type           Disp Enb Address    What
1       breakpoint     keep y   0x08048441 in main at step_in.c:15
```
