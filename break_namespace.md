
**break namespace**

```
root@lab:~/gdb-pieces# cat break_namespace.cpp 
#include <stdio.h>

namespace Foo
{
    int foo()
    { 
        return 0;
    }
}

namespace
{
    int bar()
    {
        return 1;
    }
}

int main(int argc, char *argv[])
{
    return 0;
}
```

```
root@lab:~/gdb-pieces# gdb break_namespace 
Reading symbols from break_namespace...done.
(gdb) b Foo::foo
Breakpoint 1 at 0x804846e: file break_namespace.cpp, line 7.
(gdb) b ::bar
Function "::bar" not defined.
Make breakpoint pending on future shared library load? (y or [n]) n
(gdb) b (anonymous namespace)::bar
Breakpoint 2 at 0x8048478: file break_namespace.cpp, line 15.

```
