Sparse matrices are prevalent.
Sparse matrix implementations are notoriously difficult to get right because:
* There are myriad sparse matrix formats.
* Optimizing operations on formats is difficult: implementation choices depend on hardware requirements, data access patterns, etc.

Many solver libraries provide no assistance in data structure---they have format requirements and expect valid data as input.


Sparse matrix libraries that provide data abstractions aim to address these issues.
May not provide formats compatible with the type of solver required...
Not very useful in developing new algorithms...
May not fit into ecosystem: library restrictions, performance requirements, etc.

Much ongoing research targets compilers:
* Give compiler a dense matrix program and allow it to determine storage formats when it comes across a sparse matrix.
* Tell the compiler what the sparse format is (abstractly) and allow it to worry about implementation details.

A compiler locks you in to languages that it supports.
Compiler may only target specific types of operations.

Existing software may have the following issues:
* Written in imperative langauges like C and Fortran
* Structure of sparse format interspersed with computation
* Logical steps of construction interspersed with computation

Developers may want to change sparse format to use a different solver.
ADCIRC uses ITPACKV - ELL format.
We want to try out ITPACK and Pardiso - Yale format.

Need to separate the structure complexities in the existing code in order to reason about the sparse matrix format change:
* Current implementation has data access littered throughout thousands of lines of code.
* Matrix updates across parallel nodes also interspersed.
* How will a change in sparse format change these data accesses?

Major issue in going from ELL to Yale:
* ELL format never changes array sizes, Yale format does during wetting and drying.
* Parallel Yale format? Must work with solver...