
---
`SDL_WINDOW_OPENGL` 是用于指定创建的窗口支持 [[OpenGL]] 渲染的标志。当使用 SDL 创建窗口时，可以在 `flags` 参数中传递 `SDL_WINDOW_OPENGL` 标志来指定窗口应该支持 [[OpenGL]] 渲染。

具体来说，当窗口创建时包含 `SDL_WINDOW_OPENGL` 标志时，SDL 将会为该窗口创建一个与 [[OpenGL]] 兼容的渲染上下文，从而允许在该窗口中进行 [[OpenGL]] 渲染操作。这意味着可以在这样的窗口中使用 OpenGL API 绘制图形、渲染场景等。

需要注意的是，使用 `SDL_WINDOW_OPENGL` 标志创建的窗口不一定会立即创建一个 [[OpenGL]] 上下文。实际的 [[OpenGL]] 上下文创建通常是在调用 `SDL_GL_CreateContext()` 函数后才会发生。因此，在创建带有 `SDL_WINDOW_OPENGL` 标志的窗口后，可能需要调用 `SDL_GL_CreateContext()` 函数来手动创建 [[OpenGL]] 上下文。

总之，`SDL_WINDOW_OPENGL` 标志用于指定创建的窗口支持 [[OpenGL]] 渲染，但实际的 [[OpenGL]] 上下文创建通常需要进一步的初始化步骤。