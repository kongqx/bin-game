```
root@lab:~/gdb-pieces# gdb step_in 
Reading symbols from step_in...done.
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
```


set a breakpoint on **0x08048430**, and run the program.

```
(gdb) break *main+43
Breakpoint 1 at 0x8048430: file step_in.c, line 13.
(gdb) run
Starting program: /root/gdb-pieces/step_in 

Breakpoint 1, 0x08048430 in main () at step_in.c:13
13			printf("%d\n", a);
```

enable gdb **step-mode** feature, and we can step into system function **printf**.

```
(gdb) set step-mode on
(gdb) step
__printf (format=0x80484e0 "%d\n") at printf.c:28
28	printf.c: No such file or directory.
(gdb) disassemble 
Dump of assembler code for function __printf:
=> 0xb7e6cbd0 <+0>:	push   %ebx
   0xb7e6cbd1 <+1>:	sub    $0x18,%esp
   0xb7e6cbd4 <+4>:	call   0xb7f4314b <__x86.get_pc_thunk.bx>
   0xb7e6cbd9 <+9>:	add    $0x159427,%ebx
   0xb7e6cbdf <+15>:	lea    0x24(%esp),%eax
   0xb7e6cbe3 <+19>:	mov    %eax,0x8(%esp)
   0xb7e6cbe7 <+23>:	mov    0x20(%esp),%eax
   0xb7e6cbeb <+27>:	mov    %eax,0x4(%esp)
   0xb7e6cbef <+31>:	mov    -0x70(%ebx),%eax
   0xb7e6cbf5 <+37>:	mov    (%eax),%eax
   0xb7e6cbf7 <+39>:	mov    %eax,(%esp)
   0xb7e6cbfa <+42>:	call   0xb7e63210 <_IO_vfprintf_internal>
   0xb7e6cbff <+47>:	add    $0x18,%esp
   0xb7e6cc02 <+50>:	pop    %ebx
   0xb7e6cc03 <+51>:	ret    
End of assembler dump.
```
