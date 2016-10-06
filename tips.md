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
* Learn to create and use structs.
* IDAPython is very powerful and worth learning.
* Use FLIRT whenever you see a static binary. You can save a ton of normally wasted time reverse engineering common functions.

## Debugging

### GDB

* Don't suffer through vanilla GDB. Use something like [GEF](https://github.com/hugsy/gef), [PEDA](https://github.com/longld/peda), or [Voltron](https://github.com/snare/voltron).
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
* `file` - Try to determine what type of file you have.
* `strace` - See which syscalls an executable executes.
* `ltrace` - See which library calls an executable executes.
* `ldd` - See which dynamic libraries an executable loads.
* `nm` - Dump a binary's symbols
* Readline shortcuts are _super_ handy.

  | Key      | Effect                             |
  |----------|------------------------------------|
  | `Ctrl-E` | Go to end of line                  |
  | `Ctrl-A` | Go to start of line                |
  | `Ctrl-U` | Delete everything left of cursor   |
  | `Ctrl-K` | Delete everything right of cursor  |
  | `Ctrl-W` | Delete word left                   |
  | `Ctrl-Y` | Paste last deleted text            |
  | `Ctrl-F` | Move cursor forward one char       |
  | `Ctrl-B` | Move cursor back one char          |
  | `Ctrl-P` | Move back one line in history      |
  | `Ctrl-N` | Move forward one line in history   |
  | `Ctrl-R` | Search bash history (start typing) |
  | `Ctrl-G` | Cancel history search              |
