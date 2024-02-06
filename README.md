# LiteTF
Small library for neural networks on CPU and GPU

# Build (CPU):

1. clone this repo:
   * git clone https://github.com/msu-graphics-group/LiteTF.git
   * cd LiteTF 
2. use Cmake to build project without Vulkan:
   * cmake CMakeLists.txt -DMODULE_VULKAN=OFF
   * make -j8  

# Build (GPU):

1. clone and build kernel_slicer (https://github.com/Ray-Tracing-Systems/kernel_slicer) in some directory
2. build project with Vulkan enabled and proper path to slicer
   * cmake CMakeLists.txt -DMODULE_VULKAN=ON -DSLICER_DIR="/path/to/kernel_slicer"
   * make -j8 
3. build shaders:
   * cd shaders_gpu && bash build.sh

# Launch

launch ./nn_test to run a set of tests for different features of neural networks
tests 21 and 23 require MNIST and CIFAR10 datasets and disabled by default. You can
find binary versions of these datasets yourself or ask me. However, all functions used
in these tests are covered by other tests that do no require external data.