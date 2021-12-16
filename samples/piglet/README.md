# Sample: piglet

[![Version](https://img.shields.io/badge/Version-1.00-brightgreen.svg)](https://github.com/Cryptogenic/OpenOrbis-PS4-Toolchain)

This project contains example code for the Piglet system library which is an OpenGL ES 2.0 and EGL 1.4 specs implementation.

The sample is using the GLMath library which you can download [here](https://github.com/g-truc/glm)

- **Title ID**: BREW00071
- **Content ID**: IV0000-BREW00071_00-PIGLETEXAMPLE000



## Directory structure
```
samples/piglet
|-- assets                     // Assets directory
    |-- audio
	|-- fonts
    |-- images
	    |-- rgba_texture.png   // An RGBA PNG texture that will be drawn to the screen, may be NPOT
	|-- misc
	|-- videos
|-- piglet                     // Source code directory
    |-- x64
        |-- Debug              // Object files / intermediate directory
	|-- glm                    // GLMath header-only library
    |-- build.bat              // Batch file for building on Windows
    |-- piglet.vcxproj         // Visual studio project files
    |-- piglet.vcxproj.filters
    |-- piglet.cvxproj.user
    |-- main.cpp               // main source file
	|-- ApplicationBase.hpp    // Application interface class
	|-- ApplicationBase.cpp
	|-- PigletApplication.cpp  // The actual Piglet app implementation
	|-- PigletApplication.hpp
	|-- stb_image.h            // STB header-only image library to load the texture
|-- sce_module                 // Dependency modules for the pkg
    |-- libSceFios2.prx
    |-- libc.prx
|-- sce_sys                    // Package materials (metadata)
    |-- about
        |-- right.prx
    |-- icon0.png              // Project's icon
    |-- param.sfo              // Project's parameters file (regenerated by the build script)
|-- eboot.bin                  // final eboot (not present until built)
|-- piglet.sln                 // Visual studio solution file
|-- Makefile                   // Make rules for building on Linux
|-- pkg.gp4                    // Package project file
```
The ELF, Orbis ELF (OELF), and object files will all be stored in the intermediate directory `x64/Debug`. The final eboot.bin file will be found in the root directory.



## Libraries used

- libc
- libkernel
- libc++ (libunwind implicitly linked for exception support)
- Pigletv2VSH
- PrecompiledShaders (these are used by Sony in WebKit)



## Building

A visual studio project has been included for building on Windows. On Linux, a makefile has been included.

To build this project, the developer will need clang, which is provided in the toolchain. The `OO_PS4_TOOLCHAIN` environment variable will also need to be set to the root directory of the SDK installation.

__Windows__
Open the Visual Studio project and build, or run the batch file from command prompt or powershell with the following command:
```
.\build.bat .\x64\Debug "piglet" "%OO_PS4_TOOLCHAIN%\\samples\\piglet"
```

__Linux__
Run the makefile.
```
make
```



## Author(s)

- Specter
- orbisdev and flat_z for their Piglet RE effort and headers!
- Nikita Krapivin