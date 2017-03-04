# Ideas for improving Jython

Most new work should target Jython 3.x
(https://github.com/jython/jython3); or should have a plan to target
both Jython 2.7.x and Jython 3.x.

# CExtAPI support through JyNI

Continue work on supporting the C Extension API (http://jyni.org/),
especially support for Windows.

# Implement Python bytecode compiler

Rather than compiling to Java bytecode, emit Python bytecode
instead. Note that it still may make sense to use $py.class output
instead of .pyc, but that should be a packaging option.

# CFFI

Implement support for CFFI: https://cffi.readthedocs.io/. With recent
support of large methods in Python via the use of CPython to do the
compilation, we should be able

# Port Jython grammar to Antlr 4 from Antlr 3

Such work should start by examining the grammar defined here,
https://github.com/antlr/grammars-v4/tree/master/python3, and compare
to https://github.com/jython/jython3/blob/master/grammar/Python.g It
should also take account the variant to support partial parsing for
console usage; as well as to continue to support the ast/_ast modules.

# site-packages support in a singlejar deployment

Starting with http://bugs.jython.org/issue2143, develop a packaging
solution for Lib/, including Lib/site-packages, that works with a Zip
Filesystem Provider. Such a solution needs to be compatible with all
filesystem usage, including being able to introspect metadata at the
file level.

# Implement asyncio support for Jython 3

Such work should target Netty for maximum performance, instead of the
current socket/select/ssl emulation, which also layers on Netty.

# Support MyPy for Java types

It should be possible for MyPy to typecheck Jython code, including the
use of imported Java types.

# Other ideas for Jython 3?

Please add them here by submitting a PR.
