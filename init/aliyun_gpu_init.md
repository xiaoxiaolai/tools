## 阿里云环境
```bash
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 510.47.03    Driver Version: 510.47.03    CUDA Version: 11.6     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  Tesla V100-SXM2...  On   | 00000000:00:08.0 Off |                    0 |
| N/A   41C    P0    55W / 300W |   4075MiB / 16384MiB |      0%      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|    0   N/A  N/A   1252999      C   python3                          4073MiB |
+-----------------------------------------------------------------------------+

lsb_release -a
LSB Version:	:core-4.1-amd64:core-4.1-noarch
Distributor ID:	AlibabaCloud(AliyunLinux)
Description:	Alibaba Cloud Linux (Aliyun Linux) release 2.1903 LTS (Hunting Beagle)
Release:	2.1903
Codename:	HuntingBeagle
```

### 初始化用户
useradd -r -m -G root cuijinlai

### 安装基础软件
1. [git>=2.25](../env/git.md)
2. [conda](../env/miniconda.md)
   1. conda install ipykernel(jupyter notebook运行需要的kernel和conda创建的虚拟环境并不能完全互通。利用conda创建了虚拟环境，但是启动jupyter notebook之后却找不到虚拟环境。实际上是由于在虚拟环境下缺少kernel.json文件)
3. pip
   1. pip config set global.index-url http://pypi.mirrors.ustc.edu.cn/simple/
   2. pip config set global.trusted-host  pypi.mirrors.ustc.edu.cn
4. [stable-diffusion-webui](../env/stable-diffusion-webui.md)
   1. 问题处理
      1. [GFPGAN安装失败，手动安装](../env/GFPGAN.md)
      2. Cannot locate TCMalloc (improves CPU memory usage)
         1. sudo yum install gperftools
      3. Building wheel for pycairo (pyproject.toml) did not run successfully
         1. yum install glib-devel
         2. yum install atk-devel
         3. yum install pango-devel
         4. yum install cairo-devel
5. [kohya_ss](../env/kohya_ss.md)


### 资料
### pip源
1. 阿里云 http://mirrors.aliyun.com/pypi/simple/
2. 中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/
3. 豆瓣(douban) http://pypi.douban.com/simple/
4. 清华大学 https://pypi.tuna.tsinghua.edu.cn/simple/
5. 中国科学技术大学 http://pypi.mirrors.ustc.edu.cn/simple/