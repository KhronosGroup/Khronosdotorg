# SPIR Resources and Projects

We believe the true usefulness of SPIR goes beyond the spec itself; it is an ecosystem of tools, documentation, and resources contributed by the community. You are encouraged to [get involved](https://github.com/KhronosGroup/Khronosdotorg)!

## SPIR-V Resources

* Khronos Group [SPIR-V Headers](https://github.com/KhronosGroup/SPIRV-Headers)
  official headers for SPIR-V, XML registry, and instructions set grammar in JSON form.
* [](NEW) [ARM: SPIRV-Cross](https://community.arm.com/groups/arm-mali-graphics/blog/2016/04/18/spirv-cross), working with SPIR-V in your app
* Khronos Group [SPIR-V Tools](https://github.com/KhronosGroup/SPIRV-Tools) Project including an assembler, binary module parser, disassembler, and validator for SPIR-V
  * Extras include integration with the vim and emacs text editors and the `less` command line tool
* Khronos Group [Glslang](https://github.com/KhronosGroup/glslang) - GLSL reference
  compiler.  It can generate SPIR-V.
* [LLVM framework with LLVM Support](https://github.com/KhronosGroup/SPIRV-LLVM/)  including an LLVM <-> SPIR-V bi-directional converter 
* [Shaderc](https://github.com/google/shaderc/) - `libshaderc` API and `glslc`
  command line wrapper around
  [Glslang](https://github.com/KhronosGroup/glslang).  `glslc` conventions
  mimic GCC and Clang, for ease of integration into build systems.
* [spirthon - Python](https://github.com/cheery/spirthon) Python bytecode to SPIR-V conversion; 
Write shaders or kernels in Python;
Python assembler/disassembler;
SPIR-V specification in json format
* [SpirvNet - C#](https://github.com/Philip-Trettner/SpirvNet) Write shaders or kernels in C#; .NET IL to SPIR-V conversion; SPIR-V interpreter; Debug shaders & kernels in C# (CPU)
* [otherside - C++](https://github.com/bonus2113/otherside) SPIR-V virtual machine; Produces C like code from SPIR-V binaries; Set through generated C code in debugger; Basis for academic software rasterizer
* [Shade - Xojo](https://github.com/Zoclee/Shade) SPIR-V virtual machine; Test and debug SPIR-V binaries; Defines human readable format; SPIR-V binary correctness
* [SPARV - Rust](https://github.com/fkaa/sparv) Process SPIR-V from Rust; (Dis)Assemble SPIR-V binaries
* [Go SPIR-V Library](https://github.com/jteeuwen/spirv) SPIR-V library for Go; (Dis)Assemble SPIR-V binaries; In memory representation
* [Python SPIR-V Tools](https://github.com/kristerw/spirv-tools) Encode and decode SPIR-V in Python; High level human readable assembler syntax - similar to LLVM IR
* [HSPIRV - Haskell EDSL](https://github.com/stevely/hspirv) SPIR-V like language embedded in Haskell; Low level abstraction; Significantly relaxed layout constraints
* [Lisp Specification](https://github.com/cbaggers/spir-v) Lisp readable SPIR-V specification; Basis for data driven Lisp tools
* [SPIR-V json specification](https://github.com/Philip-Trettner/SpirvSpecToJson) Conversion of HTML SPIR-V specification to json format; Basis for future data driven tools
* [vim-spirv](https://github.com/kbenzie/vim-spirv) is a plugin for vim providing automatic (dis)assembly and editing of `.spv` files, syntax highlighting, current ID highlighting and error highlighting

## SPIR Resources

* [CLANG SPIR 1.2 Generator](https://github.com/KhronosGroup/SPIR) CLANG SPIR 1.2 Generator
* [PGI OpenACC 2.0 Compiler](http://www.pgroup.com/resources/accel.htm) PGI Accelerator™ compilers, programmers can accelerate applications on x64+accelerator platforms by adding OpenACC compiler directives to existing high-level standard-compliant Fortran, C and C++ programs
* [C++ AMP CLANG/LLVM based](https://bitbucket.org/multicoreware/cppamp-driver-ng/wiki/Home) C++AMP 1.2 standard and transforms it into either SPIR binary devices
* [Halide](http://halide-lang.org/) Halide Programming language for high-performance image processing
