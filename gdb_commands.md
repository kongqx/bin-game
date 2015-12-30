
**gdb commands**

```
(gdb) 
Display all 180 possibilities? (y or n)
!                            clear                        end                          jit-reader-load              python-interactive           select-frame                 tp
+                            clone-inferior               eval                         jit-reader-unload            quit                         set                          trace
-                            collect                      exec-file                    jump                         rbreak                       sharedlibrary                tsave
<                            commands                     explore                      kill                         rc                           shell                        tstart
>                            compare-sections             file                         layout                       record                       show                         tstatus
actions                      complete                     find                         list                         refresh                      si                           tstop
add-auto-load-safe-path      condition                    finish                       load                         remote                       signal                       tty
add-inferior                 continue                     flushregs                    macro                        remove-inferiors             skip                         tui
add-symbol-file              core-file                    focus                        maintenance                  remove-symbol-file           source                       tvariable
add-symbol-file-from-memory  define                       forward-search               make                         restart                      start                        undisplay
advance                      delete                       frame                        mem                          restore                      step                         unset
agent-printf                 detach                       fs                           monitor                      return                       stepi                        until
alias                        directory                    ftrace                       next                         reverse-continue             stepping                     up
append                       disable                      function                     nexti                        reverse-finish               stop                         up-silently
apropos                      disassemble                  generate-core-file           ni                           reverse-next                 strace                       update
attach                       disconnect                   goto-bookmark                nosharedlibrary              reverse-nexti                symbol-file                  watch
awatch                       display                      handle                       output                       reverse-search               tabset                       wh
backtrace                    document                     hbreak                       overlay                      reverse-step                 target                       whatis
bookmark                     dont-repeat                  help                         passcount                    reverse-stepi                task                         where
break                        down                         if                           path                         rni                          tbreak                       while
break-range                  down-silently                ignore                       print                        rsi                          tcatch                       while-stepping
bt                           dprintf                      inferior                     print-object                 run                          tdump                        winheight
call                         dump                         info                         printf                       rwatch                       teval                        ws
catch                        echo                         init-if-undefined            ptype                        save                         tfind                        x
cd                           edit                         interpreter-exec             pwd                          search                       thbreak                      
checkpoint                   enable                       interrupt                    python                       section                      thread                       
```


**!**

```
(gdb) !ls
break_namespace  break_namespace.cpp  call_print  call_print.c	frame  frame.c	step_in  step_in.c
```


