## Install Python build dependencies
Python includes a set of modules that it builds by linking to other popular open source projects.

Many of those projects are included in Debian by default as executable programs, but the development files 
(headers, libraries) necessary to link them into Python are packaged separately 
and not included in a default Debian install.

Some of these libraries are actually required for the python build/install steps to complete successfully:

| Library                            | Python Module | Dev Package  |
| ---------------------------------- | ------------- | ------------ |
| https://www.zlib.net/              | `zlib`        | `zlib1g-dev` |
| https://www.sourceware.org/libffi/ | `_ctypes`     | `libffi-dev` |

The entries in the 'Dev Package' column are the names of packages containing the development files our python build needs.

Each of these 'dev' packages has a corresponding binary package that is probably already installed. 
So you're likely not going to be adding new pieces of software to your system by installing these. 
You're just installing the files necessary to compile new pieces of software (in our case a newer python) 
so that it can use them. (Also note that these 'dev' packages all have their corresponding binary 
packages as dependencies, so installing a dev package will ensure that its binary package is also installed.)

So let's install them:

```bash
sudo apt install zlib1g-dev libffi-dev
```

The next set of packages fall more in the 'optional' category:

| Library                                              | Python Module(s)              | Dev Package        |
| ---------------------------------------------------- | ----------------------------- | ------------------ |
| http://www.bzip.org/                                 | `_bz2`                        | `libbz2-dev`       |
| https://www.gnu.org/software/ncurses/                | `_curses` and `_curses_panel` | `libncursesw5-dev` |
| https://www.gnu.org.ua/software/gdbm/                | `_dbm` and `_gdbm`            | `libgdbm-dev`      |
| https://tukaani.org/xz/                              | `_lzma`                       | `liblzma-dev`      |
| https://www.sqlite.org/                              | `_sqlite3`                    | `libsqlite3-dev`   |
| https://www.tcl.tk/software/tcltk/                   | `_tkinter`                    | `tk-dev`           |
| https://github.com/karelzak/util-linux               | `_uuid`                       | `uuid-dev`         |
| https://tiswww.case.edu/php/chet/readline/rltop.html | `readline`                    | `libreadline-dev`  |

Python can build and install without these, and your applications might not need them. On the other hand, if you install them, the 'make' step shouldn't report any modules it was unable to build, and the binaries are already included in a default Debian install.

The command to copy-paste if you'd like to go ahead and install all of the above 'optional' packages is:

```bash
sudo apt install libbz2-dev libncursesw5-dev libgdbm-dev liblzma-dev libsqlite3-dev tk-dev uuid-dev libreadline-dev
```