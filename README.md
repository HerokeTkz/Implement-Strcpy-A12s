# Implement-Strcpy-A12s


### `undefined reference to 'stpcpy'`

This is caused by a libcall optimization added in Clang 12 that optimizes certain basic `sprintf` calls into `stpcpy` calls. The correct fix for this is to cherry-pick ["lib/string.c: implement stpcpy"](https://github.com/kdrag0n/proton_zf6/commit/cec73f0775526), which adds a simple implementation of `stpcpy` to the kernel so that Clang can use it.
