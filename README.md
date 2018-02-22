Unrpyc is a script to decompile Ren'Py (http://www.renpy.org/) compiled .rpyc
script files. It will not extract files from .rpa archives. For that, use
[rpatool](https://github.com/Shizmob/rpatool) or [UnRPA]
(https://github.com/Lattyware/unrpa).

Usage options:

Options:
```
  --version      show program's version number and exit

  -h, --help     show this help message and exit

  -c, --clobber  overwrites existing output files

  -d, --dump     Instead of decompiling, pretty print the contents
                 of the AST in a human readable format.
                 This is mainly useful for debugging.
  -p, --processes
                 use the specified number of processes to decompile
  --sl1-as-python
                 Only dumping and for decompiling screen language 1
                 screens. Convert SL1 Python AST to Python code instead
                 of dumping it or converting it to screenlang.
  --comparable   Only for dumping, remove several false differences when
                 comparing dumps. This suppresses attributes that are
                 different even when the code is identical, such as file
                 modification times.
  --no-pyexpr    Only for dumping, disable special handling of PyExpr objects,
                 instead printing them as strings. This is useful when comparing
                 dumps from different versions of Ren'Py. It should only be used
                 if necessary, since it will cause loss of information such as
                 line numbers.
  --init-offset  Attempt to guess when init offset statements were used and
                 insert them. This is always safe to enable if the game's Ren'Py
                 version supports init offset statements, and the generated code
                 is exactly equivalent, only less cluttered.
```
Usage: [python2] unrpyc.py [options] script1 script2 ...

Supported:
* renpy version 6
* Windows, OSX and Linux

Unrpyc has only been tested on versions up to 6.99.9, though newer versions are
expected to mostly work. If you find an error due to a new ren'py version being
incompatible, please open an issue.

Requirements:
* Python version 2.7
