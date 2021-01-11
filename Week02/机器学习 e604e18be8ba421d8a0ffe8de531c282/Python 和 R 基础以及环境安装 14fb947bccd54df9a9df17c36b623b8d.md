# Python 和 R 基础以及环境安装

## 环境安装

Nvidia Docker 安装：[https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker)

Nvidia Docker 启动 gpu

```bash
docker run -it --rm --gpus all -v 映射文件夹 -p 8888:8888 awesomeimage:latest
```

安装Cuda

1. disable Nouveau kernel diver
2. download cuda 使用对应系统的 runfile 安装，注意不能直接使用网站上的 runfile 命令，需要添加 `--no-opengl-libs` 参数才行

![Python%20%E5%92%8C%20R%20%E5%9F%BA%E7%A1%80%E4%BB%A5%E5%8F%8A%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85%2014fb947bccd54df9a9df17c36b623b8d/Untitled.png](Python%20%E5%92%8C%20R%20%E5%9F%BA%E7%A1%80%E4%BB%A5%E5%8F%8A%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85%2014fb947bccd54df9a9df17c36b623b8d/Untitled.png)

## Python 基础

`namedTuple` 解决必填参数的问题，不传编译会报错。

`Data Class` 解决参数传递的问题。