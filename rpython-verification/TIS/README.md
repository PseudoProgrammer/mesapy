## System Requirements and Installation

We can run TIS on standard Ubuntu. Below we outline our evaluation scripts and their verification results.


### Verification Scripts

TIS conducts the static analysis on the source code for the verification. It does not only relies on the target C program, but also the C programs of its header files.
We also need to setup some magics to make TIS run properly. ./scripts includes all required scripts to verify target C programs.


### Verification results 

The below table gives the verification results from TIS. We manually wrote all drivers to enable TIS to run on the target C program. All drivers are included under ./mock.
We need to manually check the verfied results, so not all the alarms are handled now. For TPs, we patched them and label each pach with its reason. "fix reason" is the label for the patch. Please see the patch by searching the label.

| Filename        |   Verified Result   |  LOC  |  FP | TP | Unsolved |
| -------------   | :-----------------: | ----: | ---:|--: | --------:|
| `dtoa.c`        | sat                 |  3006 |  20 |  2 |   53     |
| `asm_gcc_x86.c` | sat                 |    33 |  1  |  0 |   0      |
| `entrypoint.c`  | unsat               |   130 |  0  |  0 |   0      |
| `codemap.c`     | sat                 |   165 |  1  |  4 |   0      |
| `skiplist.c`    | sat                 |   109 |  11 |  8 |   19     |
| `debug_print.c` | unsat               |   274 |  0  |  0 |   0      |
| `entrypoint.c`  | unsat               |   130 |  0  |  0 |   0      |
| `exception.c`   | unsat               |    45 |  0  |  0 |   0      |
| `instrument.c`  | unsat               |    76 |  0  |  0 |   0      |
| `int.c`         | unsat               |    48 |  0  |  0 |   0      |
| `ll_strtod.c`   | sat                 |   145 |  15 |  0 |   0      |
| `mem.c`         | sat                 |   178 |  1  |  0 |   0      |
| `profiling.c`   | unsat               |    73 |  0  |  0 |   0      |
| `rtyper.c`      | sat                 |    38 |  2  |  0 |   0      |
| `signals.c`     | unsat               |   206 |  0  |  0 |   0      |
| `stack.c`       | sat                 |    66 |  2  |  0 |   0      |
| `support.c`     | unsat               |    27 |  0  |  0 |   0      |
| `thread.c`      | unsat               |    22 |  0  |  0 |   0      |
| `threadlocal.c` | unsat               |   273 |  0  |  0 |   0      |

### To Do List

The remaining C files to be verified are included as following:

```
${USE_SESSION_DIR}/module_cache/module_22.c
${USE_SESSION_DIR}/module_cache/module_23.c
${USE_SESSION_DIR}/module_cache/module_24.c 
${USE_SESSION_DIR}/module_cache/module_25.c 
${USE_SESSION_DIR}/module_cache/module_26.c 
${USE_SESSION_DIR}/module_cache/module_27.c 
${USE_SESSION_DIR}/module_cache/module_28.c 
${USE_SESSION_DIR}/module_cache/module_29.c 
${USE_SESSION_DIR}/module_cache/module_30.c 
${USE_SESSION_DIR}/module_cache/module_31.c 
${USE_SESSION_DIR}/module_cache/module_32.c 
${USE_SESSION_DIR}/module_cache/module_33.c 
${USE_SESSION_DIR}/module_cache/module_34.c
```

