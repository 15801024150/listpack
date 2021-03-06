Listpack: work in progress implementation
===

This repository is a work in progress, currently not usable, implementation
of a data structure called *listpack*, suitable to store lists of string
elements in a representation which is space efficient and that can be
efficiently accessed from left to right and from right to left.

You can find the specification in the `listpack.md` file in this repository.

The `listpack.c` file implements the full specification, however since
Redis Conf 2017 is near, I'll pause the work for some time to focus on
talks & training day material. The implementation lacks a complete fuzz testing
suite like the one of [rax](https://github.com/antirez/rax), the functions
to validate a listpack loaded from an untrusted source, and good API
documentation (but `listpack.c` top comments in functions are a good
starting point).

The code is almost completely untested, so it will likely explode while you
are reading this README file.

API TODO
===

    int lpIsValid(unsigned char *lp, uint32_t len);
    int lpSelfTest(void);
    int lpSplit(unsigned char *lp, unsigned char *p, unsigned char **left, unsigned char **right);
    unsigned char *lpMerge(unsigned char *left, unsigned char *right);
