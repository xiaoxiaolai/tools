### cudnn

[参考文档](https://developer.nvidia.com/rdp/cudnn-download)

rpm -i xx.rpm
yum install xx

cd /usr/src/cudnn_samples_v8/mnistCUDNN
make clean && make
./mnistCUDNN

问题
- test.c:1:23: fatal error: FreeImage.h: No such file or directory
  - sudo yum install freeimage
  - sudo yum install freeimage-devel



