# OpenCL Resource Guide

<img src="https://www.khronos.org/assets/images/api_logos/opencl.svg" width="350">

OpenCL™ is being actively evolved to meet the growing demands for the use of parallel processing to deliver higher levels of compute performance. The OpenCL Working Group at Khronos regularly extends OpenCL for enhanced functionality and flexibility, as well as increasing the quality and diversity of tools, libraries, and language compilers.

This Resource Guide is curated by the OpenCL Working Group to assist computing specialists, developers and researchers of all skill levels find documentation and tools to start effectively harnessing the power of OpenCL. The OpenCL Working Group will continuously evolve the guide and welcomes any feedback on how it can be improved via [GitHub](https://github.com/KhronosGroup/OpenCL-Docs/issues).

Khronos also hosts an [OpenCL Community Resource Page](https://www.khronos.org/opencl/community-resources/) where anyone can submit links to OpenCL resources with a pull request on [GitHub](https://github.com/KhronosGroup/Khronosdotorg/blob/master/api/opencl/resources.md)! or by emailing the webmaster at khronos.org.

### Khronos OpenCL Resources

*   [OpenCL Home Page](https://www.khronos.org/opencl/) is the starting place to discover all things OpenCL
*   [OpenCL Registry](https://www.khronos.org/registry/OpenCL/) contains the definitive OpenCL specifications and reference materials
*   [Official list of OpenCL Adopters](https://www.khronos.org/conformance/adopters/conformant-companies#opencl) that have conformant OpenCL implementations
*   List of [conformant OpenCL implementations](https://www.khronos.org/conformance/adopters/conformant-products/opencl)

### OpenCL Kernel Languages

*   [OpenCL C Kernel Language](https://www.khronos.org/registry/OpenCL) is the Khronos-defined C99-based dialect
*   [The OpenCL C Language Extensions Documentation](https://github.com/KhronosGroup/Khronosdotorg/blob/master/api/opencl/assets/OpenCL_LangExt.pdf) describes language features that can be supported by compilers in addition to standard OpenCL C
*   [C++ for OpenCL Programming Language](https://www.khronos.org/opencl/assets/CXX_for_OpenCL.html) is a community-based C++ kernel language for OpenCL that combines full OpenCL C with most features of C++17, implemented in open source Clang and LLVM

### OpenCL Kernel Language and SPIR-V Tools

List of individual tools supporting OpenCL and SPIR-V:

*   Clang is a compiler front-end for the C family of languages including OpenCL C. It is part of the [LLVM compiler infrastructure project](https://llvm.org/), and there is [information regarding OpenCL kernel language support and standard headers](https://clang.llvm.org/docs/UsersManual.html#opencl-features)
*   [Libclc](https://github.com/llvm/llvm-project/tree/main/libclc) is a generic and portable implementation of OpenCL builtin function libraries for OpenCL 1.1 - and some functions from later versions of OpenCL can be found there too
*   The [SPIRV-LLVM Translator](https://github.com/KhronosGroup/SPIRV-LLVM-Translator), is a library and tool for translating between LLVM IR and SPIR-V
*   The open source [clspv compiler](https://github.com/google/clspv) and [clvk runtime layer](https://github.com/kpet/clvk) enable OpenCL applications to be executed on Vulkan
*   [SPIR-V Tools](https://github.com/KhronosGroup/SPIRV-Tools) provide a set of utilities to process SPIR-V modules including an optimizer, linker, (dis-)assembler, and validator

This [blog](https://www.khronos.org/blog/offline-compilation-of-opencl-kernels-into-spir-v-using-open-source-tooling) contains a detailed description of how to compile OpenCL kernels offline into SPIR-V using the available open source tools.

### OpenCL Development Tools

*   Open source [OpenCL Headers](https://github.com/KhronosGroup/OpenCL-Headers)
*   Open source [OpenCL ICD Loader](https://github.com/OCL-dev/ocl-icd)
*   [Intercept Layer for OpenCL Applications](https://github.com/intel/opencl-intercept-layer) that can intercept and modify OpenCL calls for debugging and performance analysis
*   [OpenCL C++ bindings](https://github.com/KhronosGroup/OpenCL-CLHPP) to enable host code to be conveniently written using C++ abstractions

### Commercial OpenCL SDKs and Tools

*   [Intel SDK for OpenCL Applications](https://software.intel.com/en-us/intel-opencl) is a development platform for OpenCL: Maximize performance; Optimize tasks for the best available compute engine; Tap into an easy-to-use development environment
*   [Intel FPGA SDK for OpenCL](https://www.intel.com/content/www/us/en/software/programmable/sdk-for-opencl/overview.html) is a world class development environment that enables software developers to accelerate their applications by targeting heterogeneous platforms with Intel CPUs and FPGAs
*   [NVIDIA OpenCL SDK](https://developer.nvidia.com/opencl) supports a variety of GPU-accelerated libraries and high-level programming solutions that enable developers to get started quickly with GPU Computing
*   [Arm Mali GPU](https://developer.arm.com/solutions/graphics/apis/opencl) OpenCL driver and compiler as well as libraries to accelerate machine learning and neural network inferencing applications using OpenCL
*   [Radeon GPU Profiler](https://github.com/GPUOpen-Tools/Radeon-GPUProfiler) for profiling OpenCL code on AMD GPUs

### Open Source OpenCL Implementations

*   [Intel(R) Graphics Compute Runtime for OpenCL](https://github.com/intel/compute-runtime) is an open source project to converge Intel's development efforts on OpenCL compute stacks supporting the GEN graphics hardware architecture
*   [AMD ROCm](https://rocm.github.io/QuickStartOCL.html) is an open source based solution that includes [drivers](https://github.com/RadeonOpenCompute/ROCm-OpenCL-Runtime) and [compilers](https://github.com/RadeonOpenCompute/ROCm-CompilerSupport) with [installation information](https://rocm.github.io/ROCmInstall.html). Note that for Windows-based platforms OpenCL support is shipped in the [Adrenalin](https://community.amd.com/community/gaming/blog/2019/12/10/change-the-way-you-game-with-amd-radeon-software-adrenalin-2020-edition) driver
*   [TI OpenCL-DSP](http://software-dl.ti.com/mctools/esd/docs/opencl/index.html) OpenCL 1.1 implementation for SoCs with C66x DSPs such as the AM572x
*   [Portable Computing Language (POCL)](http://portablecl.org/) is an implementation framework for OpenCL platforms with diverse device types. It utilizes upstream Clang/LLVM as a kernel compilation backbone. The POCL master branch currently supports various CPUs, [open source TCE ASIPs](http://openasip.org/) , NVIDIA GPUs (via libcuda) among other devices in the same OpenCL context

### OpenCL Support on Android Devices

*   [OpenCL supported Android Devices](https://docs.google.com/spreadsheets/d/1yc7PusMEraMYEQHNA8G9gNMZUr9Hfw2sXBIFeyfnx14/edit#gid=0) - A collection of OpenCL supported Android Devices
