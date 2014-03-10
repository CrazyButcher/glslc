glslc
=====

Simple GLSL compilation checker (uses display driver)

(c) 2013-2014 Christoph Kubisch: pixeljetstream@luxinia.de
http://glslc.luxinia.de

Basic offline compiler for GLSL
Creates a dummy window and evokes the GL driver for compiling.
Can dump pseudo assembly files for NVIDIA
Basic #include handling independent of GL_ARB_shading_language_include support

Examples
--------

glslc -o output.txt -profile vertex myvertex.vs

glslc -glslversion "430 core" -o output.txt -DFOO -vertex myvertex.vs -fragment myfrag.fs

Usage
-----

glslc [options] *filename*

### Mandatory options

-*profilename*

or

-profile *profilename*

> Profilename can be: vertex, fragment, geometry, tessevaluation, tesscontrol, compute
> and must be specified prior each file name.

### Other options:

-glslversion "*string*"

> Prepends "#version *string*\n" prior macros and shader and puts // in front of #version find in shaderfile.

-separable

> Will mark the program separable (default is false) prior attaching and linking, if GL_ARB_separate_shader_objects is supported.

-o *outputfilename*

> NVIDIA drivers can output pseudo assembly file based on NV_program

-DMACRO[=VALUE]
  
> Prepends '#define MACRO VALUE' to shader. If VALUE is not specified it defaults to 1.


