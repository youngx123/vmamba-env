# vmamba-env
Record the vmamba environment setup process

**causal-conv1d** 和 **mamba-ssm** 直接使用pip安装均失败，可以采用下面链接，下载whl安装。
## 1. causal-conv1d
> https://github.com/Dao-AILab/causal-conv1d/tree/v1.0.0
## 2. mamba-ssm

> https://github.com/state-spaces/mamba/tree/v1.0.1
## 3. 'selective_scan_cuda_core' is not defined
` NameError: name 'selective_scan_cuda_core ` 问题，是跟   **`cd kernels/selective_scan && pip install . `** 这个安装不成功可能是cuda头文件没找到.

下载 `https://github.com/MzeroMiko/VMamba ` 工程, 在 **` ~/.bashrc`** 文件后面添加下述三行.
```python
按照自己的路径和cuda版本进行对应的修改
export CPATH=/usr/local/cuda-11.2/targets/x86_64-linux/include:$CPATH
export LD_LIBRARY_PATH=/usr/local/cuda-11.2/targets/x86_64-linux/lib:$LD_LIBRARY_PATH
export PATH=/usr/local/cuda-11.2/bin:$PATH
```
然后进行编译
**` cd kernels/selective_scan && pip install .`** 

> 参考
> 
> https://blog.csdn.net/weixin_42111770/article/details/131560320
>
> https://blog.csdn.net/qq_44161734/article/details/134620943
