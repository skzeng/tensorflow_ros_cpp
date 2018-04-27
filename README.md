# tensorflow\_ros

A Catkin-friendly package for utilizing the C++ API of Tensorflow.

Get Tensorflow C++ API into ROS as easy as

    find_package(catkin REQUIRED COMPONENTS
      ... your other packages ...
      tensorflow_ros
    )

See the usage example at [https://github.com/tradr-project/tensorflow_ros_test].

## Supported Tensorflow installations

1. **As a pip (Python) package:** The easiest way on Ubuntu 14.04, Just `pip install tensorflow` and that's it. GPU version supported! Can be used on newer Ubuntu versions, but with important limitations.
1. **Using [`tensorflow_catkin`](https://github.com/Skydes/tensorflow_catkin) package:** Easily compile Tensorflow for your platform. A convenient way on newer systems. Supports GPU version.
1. **Using a custom build of Tensorflow built by bazel:** The least comfortable, yet most powerful way. [Compile Tensorflow yourself using bazel](https://www.tensorflow.org/install/install_sources) and tell this package where to find it.

See below for more detail about each of the installation types and how to set them up.

## Tested compatible versions

If you successfully used this package on an untested configuration (marked with `?`), please, [tell us](https://github.com/tradr-project/tensorflow_ros/issues).

### Ubuntu 14.04 64bits, Python 2.7.6, ROS Indigo, CUDA 8.0

Version | pip tensorflow | pip tensorflow-gpu | bazel (CPU) | bazel (GPU) | tensorflow\_catkin (CPU) | tensorflow\_catkin (GPU) | CUDNN version
--- | --- | --- | --- | --- | --- | --- | ---
0.12.1 | <span style="color:green">✓</span> | <span style="color:green">✓</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | no
1.0.0  | <span style="color:green">✓</span> | <span style="color:green">✓</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | no
1.1.0  | <span style="color:green">✓</span> | <span style="color:green">✓</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 5
1.2.0  | <span style="color:green">✓</span> | <span style="color:green">✓</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 5
1.3.0  | <span style="color:green">✓</span> | <span style="color:green">✓</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 6
1.4.0  | <span style="color:green">✓</span> | <span style="color:red">N/A (wants CUDA 9+)</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 6
1.5.0  | <span style="color:green">✓</span> | <span style="color:red">N/A (wants CUDA 9+)</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 6
1.6.0  | <span style="color:green">✓</span> | <span style="color:red">N/A (wants CUDA 9+)</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 6
1.7.0  | <span style="color:green">✓</span> | <span style="color:red">N/A (wants CUDA 9+)</span> | <span style="color:green">✓</span> | <span style="color:green">✓</span> | <span style="color:green">✓</span> | <span style="color:green">✓</span> | 6

### Ubuntu 16.04 64bits, Python 2.7.6, ROS Kinetic

Version | pip tensorflow | pip tensorflow-gpu | bazel (CPU) | bazel (GPU) | tensorflow\_catkin (CPU) | tensorflow\_catkin (GPU) | CUDA, CUDNN
--- | --- | --- | --- | --- | --- | --- | ---
0.12.1| <span style="color:orange">✓, see ABI difference problems</span> | <span style="color:orange">✓, see ABI difference problems</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 8.0, no
1.0.0 | <span style="color:orange">✓, see ABI difference problems</span> | <span style="color:orange">✓, see ABI difference problems</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 8.0, 5.0
1.1.0 | <span style="color:orange">✓, see ABI difference problems</span> | <span style="color:orange">✓, see ABI difference problems</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 8.0, 5.0
1.2.0 | <span style="color:orange">✓, see ABI difference problems</span> | <span style="color:orange">✓, see ABI difference problems</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 8.0, 5.0
1.3.0 | <span style="color:orange">✓, see ABI difference problems</span> | <span style="color:orange">✓, see ABI difference problems</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 8.0, 6.0
1.4.0 | <span style="color:orange">✓, see ABI difference problems</span> | <span style="color:orange">✓, see ABI difference problems</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 8.0, 6.0
1.5.0 | <span style="color:orange">✓, see ABI difference problems</span> | <span style="color:orange">✓, see ABI difference problems</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 9.0, 7.0
1.6.0 | <span style="color:orange">✓, see ABI difference problems</span> | <span style="color:orange">✓, see ABI difference problems</span> | ? | ? | <span style="color:red">N/A</span> | <span style="color:red">N/A</span> | 9.0, 7.0
1.7.0 | <span style="color:orange">✓, see ABI difference problems</span> | <span style="color:orange">✓, see ABI difference problems</span> | <span style="color:green">✓</span> | ? | <span style="color:green">✓</span> | <span style="color:green">✓</span> | 9.0, 7.0

### Ubuntu 18.04 64bits, Python 2.7.6, ROS Melodic

Version | pip tensorflow | pip tensorflow-gpu | bazel (CPU) | bazel (GPU) | tensorflow\_catkin (CPU) | tensorflow\_catkin (GPU) | CUDA, CUDNN
--- | --- | --- | --- | --- | --- | --- | ---


### Debian Jessie 64bits, Python 2.7.6, ROS Indigo

Version | pip tensorflow | pip tensorflow-gpu | bazel (CPU) | bazel (GPU) | tensorflow\_catkin (CPU) | tensorflow\_catkin (GPU) | CUDA, CUDNN
--- | --- | --- | --- | --- | --- | --- | ---
1.3.0  | <span style="color:green">✓</span> | <span style="color:green">✓</span> | ? | ? | ? | ? | 8.0, 6

### Debian Stretch 64bits, Python 2.7.6, ROS Indigo (compiled from source)

Version | pip tensorflow | pip tensorflow-gpu | bazel (CPU) | bazel (GPU) | tensorflow\_catkin (CPU) | tensorflow\_catkin (GPU) | CUDA, CUDNN
--- | --- | --- | --- | --- | --- | --- | ---
1.4.0  | <span style="color:orange">C++ ABI problems</span> | <span style="color:orange">C++ ABI problems</span> | <span style="color:green">✓</span> | ? | ? | ? | 8.0, 6

## Pip installation

### Prerequisites

Assumes `tensorflow` or `tensorflow-gpu` pip package is installed. Ideally via pip, but custom installs are also supported (if they're either on `PYTHON_PACKAGE_PATH` or if you manually specify environment variable `TF_PIP_PATH`).

Install either using rosdep, or by calling

    sudo pip install tensorflow
    # or
    pip install --user tensorflow
    # or in a virtualenv
    pip install tensorflow

### Note

This package uses a "hack" to link against the library that's installed by pip. I have no idea if this is currently an officially supported way of accessing the C++ API, but it seems to work.

### CMake variables:

You can change these variables either in the CMake cache file, or from commandline passing e.g. `-DTF_PIP_PATH=/my/path`

- `FORCE_TF_PIP_SEARCH:BOOL` (default `OFF`): Search for the pip-installed Tensorflow even if using a system with C++11 ABI (see below for explanation).
- `DISABLE_TF_PIP_SEARCH:BOOL` (default `OFF`): Do not search for pip-installed Tensorflow at all.
- `TF_PYTHON_VERSION:STRING` (default `2.7`): The python version used by the Tensorflow installation.
- `TF_PIP_EXECUTABLE:STRING` (default `pip${TF_PYTHON_VERSION}`): Path to the `pip` executable that should be used (important to distinguish `pip2` for Python 2 and `pip3` for Python 3).
- `TF_PIP_DISABLE_SEARCH_FOR_GPU_VERSION:BOOL` (default `OFF`): Only regards the `tensorflow` pip package, even if the GPU version is installed.
- `TF_PIP_PATH:STRING` (default `""`): If the automated search process fails, manually specify path to the folder `(site|dist)-packages/tensorflow` containing e.g. `python/pywrap_tensorflow.py`.

### C++ ABI difference problems

Ubuntu systems starting with 16.04 (Xenial) are using the new C++11 ABI for all system libraries.
Until [pip bug 1707002](https://bugs.launchpad.net/ubuntu/+source/python-pip/+bug/1707002) gets resolved (if ever!), the pip-distributed Tensorflow is built againts an older C++ ABI, which is incompatible with the C++11 ABI. This means linking to the Tensorflow library will fail on such systems and there's no way around it.

The only "workaround" is to wrap all tensorflow code into a library that exposes its functions using C API (so no `std::string`s, `std::vector`s or Eigen types) and which does not link to any system library with a C++ API.
Such library can then be built separately with `-D_GLIBCXX_USE_CXX11_ABI=0`.
Then you can freely link the rest of your code using ROS, Eigen and so on to this library.

An example of this approach can be found at [kinetic-devel branch of tensorflow_ros_test](https://github.com/tradr-project/tensorflow_ros_test/tree/kinetic-devel).

A library created this way is "backwards compatible" with older systems, so it can be used everywhere.
However, separating all Tensorflow code can be a pain in the \*\*\*, so we only suggest it as a last resort option.
This is why searching for the pip-installed Tensorflow is disabled by default on systems using the new C++11 ABI (you can force it using `-DFORCE_TF_PIP_SEARCH=ON`).

## `tensorflow_catkin` installation

### Prerequisites

Add package [`tensorflow_catkin`](https://github.com/Skydes/tensorflow_catkin) to your Catkin workspace.
Read its readme to correctly set the required CMake variables (no setup needed for the CPU version).

Be prepared that the compilation will eat up a lot of RAM and take a long time. On my system with 8 concurrent build jobs, it ate around 20 GBs in the peak.
You can add `BUILD_COMMAND make -j2` and `INSTALL_COMMAND make -j2 install` to its `CMakeLists.txt/ExternalProject_Add` to limit the number of concurrent build jobs, which also decreases memory requierements.

### CMake variables

- `FORCE_TF_CATKIN_SEARCH:BOOL` (default `OFF`): Search for `tensorflow_catkin` even if Tensorflow has already been found.
- `DISABLE_TF_CATKIN_SEARCH:BOOL` (default `OFF`): Do not search for `tensorflow_catkin` at all.

## Custom compilation of Tensorflow using Bazel

### Prerequisites

Follow the [Installing TensorFlow from Sources](https://www.tensorflow.org/install/install_sources) guide up to "Configure the installation" (including), and build the C++ library with the following command:

    bazel build --config=opt --define framework_shared_object=false tensorflow:libtensorflow_cc.so

You don't need to continue with the guide building or installing the pip package (but you might be interested, because a custom-built tensorflow can provide you with higher performance even in Python).

If you encounter memory problems during the build, you can limit the used resources using the [`--local_resources`](https://docs.bazel.build/versions/master/user-manual.html#flag--local_resources) bazel option.

### CMake variables

- `FORCE_TF_BAZEL_SEARCH:BOOL` (default `OFF`): Search for bazel-compiled Tensorflow even if Tensorflow has already been found.
- `DISABLE_TF_BAZEL_SEARCH:BOOL` (default `OFF`): Do not search for bazel-compiled Tensorflow at all.
- `TF_BAZEL_LIBRARY:STRING` (default `"${CATKIN_DEVEL_PREFIX}/../libtensorflow_cc.so"`): Full path to the build `libtensorflow_cc.so` library. If you put a symlink in your Catkin workspace root, it will be picked up by the default value.
- `TF_BAZEL_SRC_DIR:STRING` (default `"${CATKIN_DEVEL_PREFIX}/../tensorflow-include-base"`): Path to the sources folder of Tensorflow (your clone of the Git repository). If you put a symlink named `tensorflow-include-base` in your Catkin workspace root, it will be picked up by the default value.
- `TF_BAZEL_USE_SYSTEM_PROTOBUF:BOOl` (default `OFF`): Whether to use system-installed protobuf includes or those distributed with Tensorflow.