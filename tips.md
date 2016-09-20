---
layout: page
title: Tips
permalink: /tips/
---

* TOC
{:toc}

## IDA
* Common hotkeys:

  | Key              | Effect                          |
  |------------------|---------------------------------|
  | `Esc`            | Go back                         |
  | `Ctrl-Enter`     | Go forward                      |
  | `H`, `Q`, `B`    | View as decimal, hex, or binary |
  | `N`/`U`          | Name/Undefine symbol            |
  | `D`, `C`, `P`    | Convert to data, code, fuction  |

## Debugging
### GDB

* Don't suffer through vanilla GDB. Use something like GEF, PEDA, or Voltron.
* Learn these!
  * `command <bp#>` - Run commands when a bp is hit.
  * `ignore <bp#> <count>` - Convert to data, code, fuction.
  * `watch|rwatch|awatch <addr> [thread <thread>] [mask <mask>]` - Break when specified address is written to, read from, or either.
  * `hbreak <addr>` - Set a hardware breakpoint.
  * `tbreak <addr>` - Set a temporary breakpoint that disappears once hit.
  * `advance <addr>` - Continue until the specified address.
  * `catch syscall [syscall]` - Convert to data, code, function.
  * `catch signal [signal]` - Convert to data, code, function.
  * `bt` - View stack frames (backtrace).
  * `up`/`down` - Move up or down to a different stack frame.

  * `set follow-fork-mode <child|parent>` - Tell gdb to either trace the parent or 'move' to the child on `fork`.
  * `set follow-exec-mode <same|new>` - Tell gdb to either trace the original target or 'move' to the new process on `exec*`.

## Shell-fu
