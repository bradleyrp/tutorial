---
layout: post
title: Why should you use a low-level language?
slug: low-level-languages
description: An exploration of C.
author: Ryan
---

Starting [here](https://www.ibm.com/developerworks/community/blogs/jfp/entry/A_Comparison_Of_C_Julia_Python_Numba_Cython_Scipy_and_BLAS_on_LU_Factorization?lang=en) ...

Let us take the sum of some numbers in `C`.

``` c
// lu.c
inline int _(int row, int col, int rows){
    return row*rows + col;
}

void det_by_lu(double *y, double *x, int N){
    int i,j,k;
    *y = 1.;

    for(k = 0; k < N; ++k){
        *y *= x[_(k,k,N)];
        for(i = k+1; i < N; ++i){
            x[_(i,k,N)] /= x[_(k,k,N)];
        }
        for(i = k+1; i < N; ++i){
            #pragma omp simd
            for(j = k+1; j < N; ++j){
                x[_(i,j,N)] -= x[_(i,k,N)] * x[_(k,j,N)];
            }
        }
    }
}
```

Import this in Python.

```
from cffi import FFI
ffi = FFI()
ffi.cdef('void det_by_lu(double *y, double *B, int N);')
C = ffi.dlopen(r"C:\Users\IBM_ADMIN\lu.dll")
c_det_by_lu = C.det_by_lu
```

Write this to a file called `simple.c`. Compile and test this.

``` bash
gcc -shared -O3 -march=native -ffast-math lu.c -o lu.dll
```

To be continued.
