# Tensorflow-1.2-optimized-builds
Pip Wheel file built for Tensorflow 1.2 with AVX2, MKL optimizations for CPU computations. Ready to use whl files for Linux with Python 2.7. 
Invoke pip install to install any of these these pip package. For more details refer to https://www.tensorflow.org/install/install_sources.


## Links to download built whl files and details of folder contents:

### Tensorflow 1.2 with MKL version 0.9 
https://drive.google.com/drive/folders/0B1iF-VlYLTeqdFFfSG0yYXRqT3c?usp=sharing 
To build this, changed MKL version to 0.9 in ./configure file ..
Buils script : 
bazel build -c opt --config=mkl --copt="-DEIGEN_USE_VML" //tensorflow/tools/pip_package:build_pip_package

### Tensorflow 1.2 with MKL version 0.9 + AVX2 optimizations 
https://drive.google.com/drive/folders/0B1iF-VlYLTeqYW5FWENlVEN1RzQ?usp=sharing
To build this, changed MKL version to 0.9 in ./configure file ..
Build script:
bazel build -c opt --copt=-mavx --copt=-mavx2 --copt=-mfma --copt=-mfpmath=both --copt="-Ofast" --copt=-msse4.2 --config=mkl --copt="-DEIGEN_USE_VML" //tensorflow/tools/pip_package:build_pip_package

### Tensorflow 1.2 with MKL version 0.7 + AVX2 optimizations 
https://drive.google.com/drive/folders/0B1iF-VlYLTeqZ0tuWk5ZN0VuTWc?usp=sharing

### Tensorflow 1.2 with MKL version 0.7
https://drive.google.com/drive/folders/0B1iF-VlYLTeqYVduTE91XzZDNkE?usp=sharing

### Tensorflow 1.2 with AVX2 optimizations
https://drive.google.com/drive/folders/0B1iF-VlYLTeqSFZrMW1UbXZ0TkE?usp=sharing
Build script:
bazel build -c opt --copt=-mavx --copt=-mavx2 --copt=-mfma --copt=-mfpmath=both --copt="-Ofast" --copt=-msse4.2 //tensorflow/tools/pip_package:build_pip_package
Example configuration for MKL+AVX optimization



srujana@srujana:~/tensorflow$ ./configure
Please specify the location of python. [Default is /usr/bin/python]: /usr/bin/python2.7
Found possible Python library paths:
  /opt/ros/kinetic/lib/python2.7/dist-packages
  /usr/local/lib/python2.7/dist-packages
  /usr/lib/python2.7/dist-packages
Please input the desired Python library path to use.  Default is [/opt/ros/kinetic/lib/python2.7/dist-packages]

Using python library path: /opt/ros/kinetic/lib/python2.7/dist-packages
Do you wish to build TensorFlow with MKL support? [y/N] y
MKL support will be enabled for TensorFlow
Do you wish to download MKL LIB from the web? [Y/n] y
Y
Please specify optimization flags to use during compilation when bazel option "--config=opt" is specified [Default is -march=native]: Do you wish to use jemalloc as the malloc implementation? [Y/n] y
jemalloc enabled
Do you wish to build TensorFlow with Google Cloud Platform support? [y/N] n
No Google Cloud Platform support will be enabled for TensorFlow
Do you wish to build TensorFlow with Hadoop File System support? [y/N] n
No Hadoop File System support will be enabled for TensorFlow
Do you wish to build TensorFlow with the XLA just-in-time compiler (experimental)? [y/N] n
No XLA JIT support will be enabled for TensorFlow
Do you wish to build TensorFlow with VERBS support? [y/N] n
No VERBS support will be enabled for TensorFlow
Do you wish to build TensorFlow with OpenCL support? [y/N] n
No OpenCL support will be enabled for TensorFlow
Do you wish to build TensorFlow with CUDA support? [y/N] n
No CUDA support will be enabled for TensorFlow
Do you wish to build TensorFlow with MPI support? [y/N] n
MPI support will not be enabled for TensorFlow
Extracting Bazel installation...
...........
INFO: Starting clean (this may take a while). Consider using --async if the clean takes more than several minutes.
Configuration finished

Bazel build script to use MKL opts:

bazel build -c opt --copt=-mavx --copt=-mavx2 --copt=-mfma --copt=-mfpmath=both --copt="-Ofast" --copt=-msse4.2 --config=mkl --copt="-DEIGEN_USE_VML" //tensorflow/tools/pip_package:build_pip_package





