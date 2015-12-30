
```
root@lab:~/gdb-pieces# readelf -h step_in
ELF Header:
  Magic:   7f 45 4c 46 01 01 01 00 00 00 00 00 00 00 00 00 
  Class:                             ELF32
  Data:                              2's complement, little endian
  Version:                           1 (current)
  OS/ABI:                            UNIX - System V
  ABI Version:                       0
  Type:                              EXEC (Executable file)
  Machine:                           Intel 80386
  Version:                           0x1
  Entry point address:               0x8048300
  Start of program headers:          52 (bytes into file)
  Start of section headers:          4564 (bytes into file)
  Flags:                             0x0
  Size of this header:               52 (bytes)
  Size of program headers:           32 (bytes)
  Number of program headers:         8
  Size of section headers:           40 (bytes)
  Number of section headers:         35
  Section header string table index: 32
```


```
(gdb) info files 
Symbols from "/root/gdb-pieces/step_in".
Local exec file:
	`/root/gdb-pieces/step_in', file type elf32-i386.
	Entry point: 0x8048300
	0x08048134 - 0x08048147 is .interp
	0x08048148 - 0x08048168 is .note.ABI-tag
	0x08048168 - 0x0804818c is .note.gnu.build-id
	0x0804818c - 0x080481ac is .gnu.hash
	0x080481ac - 0x080481fc is .dynsym
	0x080481fc - 0x08048248 is .dynstr
	0x08048248 - 0x08048252 is .gnu.version
	0x08048254 - 0x08048274 is .gnu.version_r
	0x08048274 - 0x0804827c is .rel.dyn
	0x0804827c - 0x08048294 is .rel.plt
	0x08048294 - 0x080482b7 is .init
	0x080482c0 - 0x08048300 is .plt
	0x08048300 - 0x080484d2 is .text
	0x080484d4 - 0x080484e8 is .fini
	0x080484e8 - 0x080484f4 is .rodata
	0x080484f4 - 0x08048528 is .eh_frame_hdr
	0x08048528 - 0x08048604 is .eh_frame
	0x08049604 - 0x08049608 is .init_array
	0x08049608 - 0x0804960c is .fini_array
	0x0804960c - 0x08049610 is .jcr
	0x08049610 - 0x080496f8 is .dynamic
	0x080496f8 - 0x080496fc is .got
	0x080496fc - 0x08049714 is .got.plt
	0x08049714 - 0x0804971c is .data
	0x0804971c - 0x08049720 is .bss
```

break on the entry of program

```
(gdb) break *0x8048300
```
