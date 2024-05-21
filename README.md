## Install dev libs

```bash
sudo apt install python3-dev build-essential libbz2-dev libncursesw5-dev libgdbm-dev liblzma-dev libsqlite3-dev \
tk-dev uuid-dev libreadline-dev zlib1g-dev libffi-dev libssl-dev curl gcc libev-dev libncurses-dev make wget
```
## Build needed python versions
1. Install needed python sources - https://www.python.org/downloads/
2. Configure and install python:
```bash
./configure \
    --prefix={path/to/python} \
    --enable-shared \
    --enable-optimizations \
    --enable-ipv6 \
    LDFLAGS=-Wl,-rpath={path/to/python}/lib,--disable-new-dtags && make && LD_LIBRARY_PATH=. make install
```
## Build databases
### Clickhouse
1. https://clickhouse.com/docs/ru/getting-started/install#from-single-binary - install from single binary
2. setup systemd from service file example
### PostgreSQL
1. https://www.postgresql.org/ftp/source/ - download sources
2. Create user postgres:
```shell
useradd -m -s /bin/bash postgres && passwd postgres
```
3. Install sources to postgres home
4. Chmod rights to bin dir 