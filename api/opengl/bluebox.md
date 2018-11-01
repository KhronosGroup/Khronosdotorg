### OpenGL 4.6 at a glance

The OpenGL 4.6 and OpenGL Shading Language 4.60 Specifications were released on July 31, 2017.

New features of OpenGL 4.6 include:

*  [_GL_ARB_gl_spirv_](/registry/OpenGL/extensions/ARB/ARB_gl_spirv.txt) and [_GL_ARB_spirv_extensions_](/registry/OpenGL/extensions/ARB/ARB_spirv_extensions.txt)
to standardize SPIR-V support for OpenGL
*  [_GL_ARB_indirect_parameters_](/registry/OpenGL/extensions/ARB/ARB_indirect_parameters.txt) and [_GL_ARB_shader_draw_parameters_](/registry/OpenGL/extensions/ARB/ARB_shader_draw_parameters.txt)
for reducing the CPU overhead associated with rendering batches of geometry
*  [_GL_ARB_pipeline_statistics_query_](/registry/OpenGL/extensions/ARB/ARB_pipeline_statistics_query.txt) and [_GL_ARB_transform_feedback_overflow_query_](/registry/OpenGL/extensions/ARB/ARB_transform_feedback_overflow_query.txt)
standardize OpenGL support for features available in Direct3D
*  [_GL_ARB_texture_filter_anisotropic_](/registry/OpenGL/extensions/ARB/ARB_texture_filter_anisotropic.txt)
(based on [GL_EXT_texture_filter_anisotropic](/registry/OpenGL/extensions/EXT/EXT_texture_filter_anisotropic.txt)) brings previously IP encumbered functionality into OpenGL to improve the visual quality of textured scenes
*  [_GL_ARB_polygon_offset_clamp_](/registry/OpenGL/extensions/ARB/ARB_polygon_offset_clamp.txt)
 (based on [GL_EXT_polygon_offset_clamp](/registry/OpenGL/extensions/EXT/EXT_polygon_offset_clamp.txt)) suppresses a common visual artifact known as a “light leak” associated with rendering shadows
*  [_GL_ARB_shader_atomic_counter_ops_](/registry/OpenGL/extensions/ARB/ARB_shader_atomic_counter_ops.txt) and [_GL_ARB_shader_group_vote_](/registry/OpenGL/extensions/ARB/ARB_shader_group_vote.txt)
add shader intrinsics supported by all desktop vendors to improve functionality and performance
*  [_GL_KHR_no_error_](/registry/OpenGL/extensions/KHR/KHR_no_error.txt)
reduces driver overhead by allowing the application to indicate that it expects error-free operation so errors need not be generated

New extensions to OpenGL 4.6 include:

*   [GL_KHR_parallel_shader_compile](/registry/OpenGL/extensions/KHR/KHR_parallel_shader_compile.txt)
*   [WGL_ARB_create_context_no_error](/registry/OpenGL/extensions/ARB/ARB_create_context_no_error.txt)
*   [GLX_ARB_create_context_no_error](/registry/OpenGL/extensions/ARB/ARB_create_context_no_error.txt)
*   [GL_EXT_memory_object](/registry/OpenGL/extensions/EXT/EXT_external_objects.txt)
*   [GL_EXT_memory_object_fd](/registry/OpenGL/extensions/EXT/EXT_external_objects_fd.txt)
*   [GL_EXT_memory_object_win32](/registry/OpenGL/extensions/EXT/EXT_external_objects_win32.txt)
*   [GL_EXT_semaphore](/registry/OpenGL/extensions/EXT/EXT_external_objects.txt)
*   [GL_EXT_semaphore_fd](/registry/OpenGL/extensions/EXT/EXT_external_objects_fd.txt)
*   [GL_EXT_semaphore_win32](/registry/OpenGL/extensions/EXT/EXT_external_objects_win32.txt)
*   [GL_EXT_win32_keyed_mutex](/registry/OpenGL/extensions/EXT/EXT_win32_keyed_mutex.txt)

### API & GLSL specifications

*   [OpenGL 4.6 Core Profile Specification](/registry/OpenGL/specs/gl/glspec46.core.pdf)
*   [OpenGL 4.6 Compatibility Profile Specification](/registry/OpenGL/specs/gl/glspec46.compatibility.pdf)
*   [OpenGL Shading Language 4.60 Specification](/registry/OpenGL/specs/gl/GLSLangSpec.4.60.pdf)

### Additional Links

Specifications and documentation for the OpenGL API and OpenGL Shading Language, as well as related APIs such as GLX, are available from [OpenGL.org](https://www.opengl.org/):

*   [OpenGL Registry](/registry/OpenGL/index_gl.php)
*   [OpenGL Libraries, Tools, etc. (formerly &quot;SDK&quot;)](/registry/OpenGL-Refpages)
*   [OpenGL Reference Pages](/registry/OpenGL-Refpages/gl4/)
*   [OpenGL Reference Cards](https://www.khronos.org/developers/reference-cards/)
*   [OpenGL Resources](https://www.khronos.org/opengl/wiki)
