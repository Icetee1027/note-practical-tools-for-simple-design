
---
`SDL_GL_CONTEXT_PROFILE_MASK` 是用于设置 [[OpenGL]] 渲染上下文配置的属性之一，它指定了请求创建的 [[OpenGL]] 上下文的配置文件类型。

在使用 SDL 创建 [[OpenGL]] 渲染上下文时，可以使用 [[SDL_GL_SetAttribute()]]函数设置 `SDL_GL_CONTEXT_PROFILE_MASK` 属性，并将其值设置为下列之一：

- `SDL_GL_CONTEXT_PROFILE_CORE`：请求创建一个核心（Core）配置的 [[OpenGL]] 渲染上下文。核心配置提供了严格遵循 [[OpenGL]] 标准的特性集合，不包含已经被标记为废弃或不推荐使用的特性。
  
- `SDL_GL_CONTEXT_PROFILE_COMPATIBILITY`：请求创建一个兼容性（Compatibility）配置的 [[OpenGL]] 渲染上下文。兼容性配置提供了与旧版 [[OpenGL]] 兼容的特性，并允许使用旧版 [[OpenGL]] 的特性和扩展。

- `SDL_GL_CONTEXT_PROFILE_ES`：请求创建一个 [[OpenGL]] ES 配置的 [[OpenGL]] 渲染上下文。这种配置适用于 OpenGL ES 环境，提供了与 OpenGL ES 兼容的特性集合。

这些选项用于指定所需的 OpenGL 上下文配置文件类型，从而创建相应类型的 [[OpenGL]] 渲染上下文。需要注意的是，具体能够创建的 OpenGL 上下文配置还受到其他因素的影响，如 OpenGL 实现和驱动程序的支持情况等。