# The OpenGL Test

## About

This is my implementation of [TheCherno's OpenGL series](https://www.youtube.com/watch?v=W3gAzLwfIP0&list=PLlrATfBNZ98foTJPJ_Ev03o2oq3-GGOS2), which uses GLFW, GLEW, GLM and imgui as extension tools.

Also, refer to [docs.gl](https://docs.gl/) for the use of all OpenGL functions.

## Visual Sudio

首先是对Visual Sudio工作目录做的一些设置，来确保项目工作目录保持干净整洁。

Click：Property -> Configuration Properties -> General

- All Configurations & All Platforms

- Output Directory: `$(SolutionDir)bin\$(ProjectName)\$(Platform)\$(Configuration)\`
- Intermediate Directory: `$(SolutionDir)bin\$(ProjectName)\intermediates\$(Platform)\$(Configuration)\`

## GLFW

> GLFW is an Open Source, multi-platform library for OpenGL, OpenGL ES and Vulkan development on the desktop. It provides a simple API for creating windows, contexts and surfaces, receiving input and events.
> GLFW is written in C and supports Windows, macOS, X11 and Wayland.

当前项目用到是 GLFW 3.3.8 32-bit 的 [静态链接库](./Dependencies/GLFW/)。

```cpp
    /**
    * 设置附加包含目录
    * 项目 => OpenGL属性 => C\C++ => 常规 => 附加包含目录
    * 添加: $(SolutionDir)Dependencies\GLFW\include
    * 设置附加库目录
    * 项目 => OpenGL属性 => 链接器 => 常规 => 附加库目录
    * 添加: $(SolutionDir)Dependencies\GLFW\lib-vc2019
    * 设置附加依赖项
    * 项目 => OpenGL属性 => 链接器 => 输入 => 附加依赖项
    * 添加: glfw3.lib;opengl32.lib
    ** /
```

## GLEW

> The OpenGL Extension Wrangler Library (GLEW) is a cross-platform open-source C/C++ extension loading library. GLEW provides efficient run-time mechanisms for determining which OpenGL extensions are supported on the target platform. OpenGL core and extension functionality is exposed in a single header file. GLEW has been tested on a variety of operating systems, including Windows, Linux, Mac OS X, FreeBSD, Irix, and Solaris.

当前项目用到是 [GLEW 2.1.0 32-bit](./Dependencies/GLEW/)。

```cpp
  /**
   * 设置附加包含目录
   * 项目 => OpenGL属性 => C\C++ => 常规 => 附加包含目录
   * 添加: $(SolutionDir)Dependencies\GLEW\include
   * 设置附加库目录
   * 项目 => OpenGL属性 => 链接器 => 常规 => 附加库目录
   * 添加: $(SolutionDir)Dependencies\GLEW\lib\Release\Win32
   * 设置附加依赖项
   * 项目 => OpenGL属性 => 链接器 => 输入 => 附加依赖项
   * 添加: glew32s.lib
   * 设置预处理器定义
   * 项目 => OpenGL属性 => C\C++ => 预处理器 => 预处理器定义
   * 添加: GLEW_STATIC
   ** /
```

## Others

此外用到的其他扩展有 [stb_image](https://github.com/nothings/stb/blob/master/stb_image.h)、[GLM 0.9.9.8](https://github.com/g-truc/glm) 以及 [IMGUI 1.60](https://github.com/ocornut/imgui)。所有这些扩展均放在 `src/vendor` 中。

```cpp
  /**
   * 设置附加包含目录
   * 项目 => OpenGL属性 => C\C++ => 常规 => 附加包含目录
   * 添加: src\vendor;src
   ** /
```
