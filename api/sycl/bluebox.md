### SYCL 1.2.1

SYCL 1.2.1 revision 7 is now the latest release as of April 27,
2020, is based on OpenCL 1.2, and is a major update representing 5
years of work by Khronos members. The new specification incorporates
significant experience gained from 5 separate implementations and
feedback from developers of machine learning frameworks such as
TensorFlow, which now supports SYCL alongside the original CUDA
accelerator back-end.

*   [SYCL 1.2.1](https://www.khronos.org/registry/SYCL/)
*   [Open-source SYCL specification files](https://github.com/KhronosGroup/SYCL-Docs/)
*   [Open-source SYCL conformance test suite](https://github.com/KhronosGroup/SYCL-CTS/)
*   [SYCL Forum](https://forums.khronos.org/showthread.php/13634-Official-SYCL-1-2-1-feedback-thread) - the best place for posting your questions and feedback
*   [SYCL Press Release](https://www.khronos.org/news/press/the-khronos-group-releases-finalized-sycl-1.2.1)
*   [ComputeCpp](https://www.codeplay.com/products/computesuite/computecpp) - SYCL implementation by Codeplay
*   [triSYCL](https://github.com/triSYCL/triSYCL) - an open-source implementation to experiment with SYCL
*   [SYCL Ecosystem Website](http://sycl.tech) - SYCL community website maintained by Codeplay
* SYCL Adopters Program - [Adopters area](https://www.khronos.org/sycl/adopters/) & [Press Release](https://www.khronos.org/news/press/khronos-releases-conformance-test-suite-for-sycl-1.2.1)

SYCL 1.2.1 builds on the features of C++11, with additional support
for C++14 and C++17, enabling ISO C++17 Parallel STL programs to be
accelerated on OpenCL devices. To support this effort, Khronos is
backing an open-source project to support Parallel STL on top of SYCL,
running on OpenCL devices. This project is hosted on
[Github](https://github.com/KhronosGroup/SyclParallelSTL). So, while
SYCL brings the power of single-source modern C++ to the OpenCL and
SPIR world, it also prepares the convergence with other standards such
as Khronos' Vulkan, OpenVX and NNEF and ISO C++ (SG1, SG6, SG12, SG14,
SG19).

### SYCL 1.2

*   [SYCL 1.2](https://www.khronos.org/registry/SYCL/)
*   [SYCL Press Release](https://www.khronos.org/news/press/khronos-releases-sycl-1.2-final-specification-c-single-source-heterogeneous)
*   [SYCL 1.2 Overview slide](https://www.khronos.org/assets/uploads/developers/library/2015-iwocl/Khronos-SYCL-May15.pdf) (presentation slides in .pdf format)
*   [Tutorial on using SYCL](http://codeplaysoftware.github.io/iwocl2015/) - at the May 2015 IWOCL OpenCL conference
*   [Open-source project](https://github.com/KhronosGroup/SyclParallelSTL) to implement the proposed C++ 17 Parallel STL
*   [SYCL 1.2 Reference Guide](https://www.khronos.org/files/sycl/sycl-12-reference-card.pdf)

These SYCL 1.2 specification and conformance tests were released on May 11, 2015 and includes the following features:

* Templates and lambda functions for higher-level application software that can be cleanly coded for optimized acceleration across the extensive range of shipping OpenCL 1.2 implementations.
* Can be implemented to work with a variety of existing and new C++ compilers and layers over OpenCL 1.2 implementations from diverse vendors.
* Builds on the features of C++11, with additional support for C++14 and also will enable C++17 Parallel STL programs to be accelerated on OpenCL devices in the future.
* Developers can program at a higher level than OpenCL C, but always have access to existing code through seamless integration with OpenCL programs, C/C++ libraries and frameworks such as OpenMP
* OpenCL's interop capability is inherited by SYCL to enable applications to use SYCL in conjunction with OpenGL, DirectX and the upcoming Vulkan API without memory-copy overhead.
* Can be implemented to work with a variety of existing and new C++ compilers and layers over OpenCL 1.2 implementations from diverse vendors.

Builds on the features of C++11, with additional support for C++14 and also will enable C++17 Parallel STL programs to be accelerated on OpenCL devices in the future.
