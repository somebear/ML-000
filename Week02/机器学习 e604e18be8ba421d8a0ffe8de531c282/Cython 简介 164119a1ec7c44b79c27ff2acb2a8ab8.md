# Cython 简介

Cython 是 Python 的 superset。全部的 Python 代码袋子可以运行，但是不是它的长项。更好的方法是把它想象成 C。

Cython 和 Python 最大的区别是静态类，另一个额外的作用是代码保护。

Cython 原理是将 Python 转成 C 或 C++，然后编译。

## Cython 的编译

见 hello 文件夹及注释。

注意：

- 运行命令 `python [setup.py](http://setup.py) install`
- 注意：Cython 的建议是每个文件是一个 module。所以建议 install 来配置（docker）
- 同理：Cython 互相引用会出很多问题
- 很多时候你可能希望用 intel 编译器，但是很多时候会出很多问题。

```python
from distutils.core import setup, Extension
from Cython.Build import cythonize
import numpy

compile_flags = ['-std=c++11',  '-fopenmp']
linker_flags = ['-fopenmp']

module = Extension('hello',
                   ['hello.pyx'],
                   language='c++',
                   include_dirs=[numpy.get_include()], # This helps to create numpy
                   extra_compile_args=compile_flags,
                   extra_link_args=linker_flags)

setup(
    name='hello',
    ext_modules=cythonize(module),
    gdb_debug=True # This is extremely dangerous; Set it to False in production.
)
```

Cython 和 C 结合使用：

Cython 做数据预处理，C 做最复杂的计算

用 `cpdef` 定义的函数C和Python都可以引用，而 `cdef` 定义的Python无法引用，建议直接使用 `cpdef`。