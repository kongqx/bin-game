
**info functions**

```
root@lab:~/gdb-pieces# gdb frame 
Reading symbols from frame...done.
(gdb) info functions 
All defined functions:

File frame.c:
int func1(int);
int func2(int);
int func3(int);
int main(void);

Non-debugging symbols:
0x08048294  _init
0x080482d0  printf@plt
0x080482e0  __gmon_start__@plt
0x080482f0  __libc_start_main@plt
0x08048300  _start
0x08048330  __x86.get_pc_thunk.bx
0x08048340  deregister_tm_clones
0x08048370  register_tm_clones
0x080483b0  __do_global_dtors_aux
0x080483d0  frame_dummy
0x08048490  __libc_csu_init
0x08048500  __libc_csu_fini
0x08048504  _fini
(gdb) 

```
