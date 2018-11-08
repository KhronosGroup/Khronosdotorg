## OpenGL SC 2.0

The Safety Critical Profile for [OpenGL ES 2.0](https://www.khronos.org/opengles) is designed to be deterministic and testable to minimize implementation and safety certification costs – while bringing GLSL shader programmability to safety critical graphics for enhanced graphics functionality with increased performance and reduced power. The OpenGL SC 2.0 API addresses the unique and stringent requirements of high reliability display system markets, including FAA DO-178C and EASA ED-12C Level A for avionics, and ISO 26262 safety standards for automotive systems. Building on the large number of worldwide customer deployments and successful avionics certifications using OpenGL SC 1.0, OpenGL SC 2.0 enables high reliability system manufacturers to take advantage of modern graphics programmable shader engines while still achieving the highest levels of safety certification.

*   The OpenGL SC 2.0 core API specification and header file are in the [OpenGL SC API Registry](https://www.khronos.org/registry/OpenGL/index_sc.php)
*   Leave a comment on the OpenGL SC 2.0 feedback thread on the [Khronos forums](https://forums.khronos.org/showthread.php/13049-Official-OpenGL-SC-2-0-feedback)

NOTE: The current API definition and header are **not** MISRA-C compliant. This was a deliberate choice in order for code to be compatible with OpenGL ES 2.0, which OpenGL SC 2.0 is based on. If this, or any other safety compliance of the API is an issue for you, please [get in contact with us](https://www.khronos.org/about/technical-support/).

## OpenGL SC 1.0

The Safety Critical Profile for OpenGL is defined to meet the unique requirements of the for safety-critical applications such as avionics and automotive instrumentation displays. OpenGL SC 1.0 removes functionality from [OpenGL ES 1.0](https://www.khronos.org/opengles) to minimize implementation and safety certification costs. It also adds functionality, such as display lists, that are required to support legacy and auto-generated display applications in safety critical markets.

**For Safety Critical applications**: OpenGL SC 1.0 is defined relative to the [OpenGL 1.3 specification](https://www.khronos.org/registry/OpenGL/specs/gl/glspec13.pdf) and is designed to meet the needs of the safety critical market in Avionics, Industrial, Military and Automotive applications including D0178-B certification.

* The OpenGL SC 1.0 core API specification and header file, as well as the guiding philosophy document, are in the [OpenGL SC API Registry](https://www.khronos.org/registry/OpenGL/index_sc.php)
