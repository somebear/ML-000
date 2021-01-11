# Cython 的使用建议

Cython的使用建议：

1. 所有类型均应该有 type
2. 注意 numpy 的排列
3. 尽量使用 C++ 自带数据结构
4. 通用方法：numpy 使用 view 传递给 C 使用；C 使用 openmp 或者Eigen。使用 Map 可以适用类似的 matlab 的语法，但是不支持 OpenMP。
5. 所有内存分配和传递都应该在 Python 中完成。临时变量用 C++ 类进行构建。