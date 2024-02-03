
---
`SDL_GL_CONTEXT_PROFILE_CORE` 是一个 [[OpenGL]] 上下文的配置属性，用于指定请求创建的 [[OpenGL]] 渲染上下文的配置文件类型。

在使用 SDL 创建 [[OpenGL]] 渲染上下文时，可以使用 [[SDL_GL_SetAttribute()]]函数设置 `SDL_GL_CONTEXT_PROFILE_MASK` 属性，并将其值设置为 `SDL_GL_CONTEXT_PROFILE_CORE`，以请求创建一个核心（Core）配置的 OpenGL 渲染上下文。

核心配置的 OpenGL 渲染上下文提供了严格遵循 OpenGL 标准的特性集合，不包含已经被标记为废弃或者不推荐使用的特性。这种配置适用于现代的 OpenGL 应用程序开发，可以帮助开发者避免使用过时的特性，以提高代码的兼容性和可移植性。

需要注意的是，具体能够创建的 OpenGL 上下文配置还受到其他因素的影响，如 OpenGL 实现和驱动程序的支持情况等。
```c++
SDL_GL_CONTEXT_PROFILE_CORE = 1
```