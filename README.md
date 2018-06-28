# ZFS Channel Program Demos

This repository contains sample ZFS channel programs and demonstrates their use
through [py-libzfs][].

[py-libzfs]: https://github.com/freenas/py-libzfs

## Dependencies

The dependencies listed in `requirements.txt` are required in order to run these
demos.  To install the dependencies, you will need to have `Cython` and `six`
already installed for the version of Python you intend to use, and FreeBSD
sources must be installed to `/usr/src`.  Then run
```sh
pip install -r requirements.txt
```

## Usage

ZFS channel programs require root privileges to be run.

```sh
sudo ./zcp
```

To watch for `zfs.debug()` messages:
```sh
sudo dtrace -n 'zfs-dbgmsg{trace(stringof(arg0))}' | grep ZCP
```
