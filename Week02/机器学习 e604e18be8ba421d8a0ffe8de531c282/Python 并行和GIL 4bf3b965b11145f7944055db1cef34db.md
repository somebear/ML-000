# Python 并行和GIL

由于 Python 中 GIL(Global Interpreter Log) 的存在，使得本质上 python 只能用一个进程进行。所以这使得并行 Python 十分困难。

Python 自带的多进程库很烂，建议使用 Ray。

Ray 的长处是可以调用任何 python 函数，并可以共享数据（使得不用 copy），但是共享的数据只读（解决 race condition 问题）。

ray 的语法见项目 ray 文件夹。