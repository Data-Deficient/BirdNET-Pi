# Pre-packaged python libraries

I precompiled some of the libraries that would take to much to compile, as normally there aren't pre-built python modules for riscv64.

## Building instructions

```
sudo apt-get install -y python3-dev ccache python3-pybind11 python3-pip
export PATH=/usr/lib/ccache/:$PATH
pip3 install build
cd name-of-python-module
python3 -m build --wheel
ls -lh dist/
```

*Note:* For Tensorflow, run:

```
sudo apt install -y cmake ninja-build
BUILD_NUM_JOBS=$(nproc) PYTHON=python3 tensorflow/lite/tools/pip_package/build_pip_package_with_cmake.sh riscv64
```
