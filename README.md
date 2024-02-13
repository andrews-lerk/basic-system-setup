## Install Python build dependencies
Python includes a set of modules that it builds by linking to other popular open source projects.

| Library                                              | Python Module                 | Dev Package        |
| ---------------------------------------------------- | ----------------------------- | ------------------ |
| https://www.zlib.net/                                | `zlib`                        | `zlib1g-dev`       |
| https://www.sourceware.org/libffi/                   | `_ctypes`                     | `libffi-dev`       |
| https://www.openssl.org/                             | `_ssl`                        | `libssl-dev`       |
| http://www.bzip.org/                                 | `_bz2`                        | `libbz2-dev`       |
| https://www.gnu.org/software/ncurses/                | `_curses` and `_curses_panel` | `libncursesw5-dev` |
| https://www.gnu.org.ua/software/gdbm/                | `_dbm` and `_gdbm`            | `libgdbm-dev`      |
| https://tukaani.org/xz/                              | `_lzma`                       | `liblzma-dev`      |
| https://www.sqlite.org/                              | `_sqlite3`                    | `libsqlite3-dev`   |
| https://www.tcl.tk/software/tcltk/                   | `_tkinter`                    | `tk-dev`           |
| https://github.com/karelzak/util-linux               | `_uuid`                       | `uuid-dev`         |
| https://tiswww.case.edu/php/chet/readline/rltop.html | `readline`                    | `libreadline-dev`  |

The command to copy-paste if you'd like to install all of these packages include `python3-dev` and `build-essential`:

```bash
sudo apt install python3-dev build-essential libbz2-dev libncursesw5-dev libgdbm-dev liblzma-dev libsqlite3-dev \
tk-dev uuid-dev libreadline-dev zlib1g-dev libffi-dev libssl-dev curl gcc libev-dev libncurses-dev make wget
```

Configure python:
```bash
./configure \
    --prefix=/path/to/python \
    --enable-shared \
    --enable-optimizations \
    --enable-ipv6 && make && make install
```
