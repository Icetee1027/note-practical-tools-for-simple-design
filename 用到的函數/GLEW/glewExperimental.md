
---
`glewExperimental` 是 [[GLEW]] 库中的一个全局变量，用于指示是否启用实验性的 [[OpenGL]] 扩展加载方法。

当设置 `glewExperimental` 为 `GL_TRUE` 时，表示启用实验性的扩展加载方法。在这种情况下，[[GLEW]] 将尝试加载所有 [[OpenGL]] 扩展，即使它们可能不是标准的 [[OpenGL]] 扩展，也可能不被当前 [[OpenGL]] 上下文所支持。这种做法可能会导致加载一些不稳定或者不受支持的扩展，因此被称为实验性的。

默认情况下，`glewExperimental` 被设置为 `GL_FALSE`，表示不启用实验性的扩展加载方法。在这种情况下，[[GLEW]] 只会加载被当前 [[OpenGL]] 上下文所支持的标准 [[OpenGL]] 扩展，以确保稳定性和兼容性。

通常情况下，如果需要加载实验性的 [[OpenGL]] 扩展，可以在调用 [[用到的函數/GLEW/glewInit()]] 函数之前将 `glewExperimental` 设置为 `GL_TRUE`。然后，调用 [[用到的函數/GLEW/glewInit()]] 函数初始化 [[GLEW]]，以启用实验性的扩展加载方法。