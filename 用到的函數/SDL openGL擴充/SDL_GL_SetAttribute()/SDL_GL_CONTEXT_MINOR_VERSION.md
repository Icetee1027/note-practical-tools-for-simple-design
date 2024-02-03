
---
`SDL_GL_CONTEXT_MINOR_VERSION` 是一个 [[OpenGL]] 上下文的配置属性，用于指定请求创建的 [[OpenGL]] 渲染上下文的次版本号。

在使用 SDL 创建 [[OpenGL]] 渲染上下文时，可以使用 [[SDL_GL_SetAttribute()]]函数设置 `SDL_GL_CONTEXT_MINOR_VERSION` 属性，以请求创建指定次版本号的 [[OpenGL]] 上下文。这个属性的值应该是一个整数，表示所请求的 OpenGL 上下文的次版本号。

例如，如果要请求创建一个 OpenGL 上下文的主版本号为 3、次版本号为 2 的上下文，可以这样设置：

```c
SDL_GL_SetAttribute(SDL_GL_CONTEXT_MAJOR_VERSION, 3);
SDL_GL_SetAttribute(SDL_GL_CONTEXT_MINOR_VERSION, 2);
```

这将告诉 SDL 请求创建一个主版本号为 3、次版本号为 2 的 OpenGL 渲染上下文。需要注意的是，具体能够创建的 OpenGL 上下文版本还受到其他因素的影响，如 OpenGL 实现和驱动程序的支持情况等。