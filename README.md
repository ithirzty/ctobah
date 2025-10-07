# ctobah - Create bindings for C libraries

This is meant to be a fully automatic way of creating bindings for the Bah programming language.

For now, bindings are made of function definitions, enums, typedefs, struct/union declarations. #define macros are not available in the binding as ctobah ask the C compiler to preprocess the header file.

Dependencies:
- any c compiler (mendatory)
- pck-config (optional)

> This is still work in progress.

## Instalation

```bash
git clone https://github.com/ithirzy/ctobah
cd ctobah
./linux_install.sh
```

## Usage

You can build a command as `ctobah path/to/my/header.h -flags`
where flags can be:
- `-o`: the output file
- `-l`: the C libraries to link against
- `-w`: only print warning messages

### Example

The command `ctobah /usr/include/xcb/xcb.h -o xcb.bah -l "xcb"` will create a binding file "xcb.bah" inside the current working directory, based on the xcb.h C header file. It will also import the xcb C library (-lxcb)