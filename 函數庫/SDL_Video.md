
----
`SDL_video` 是 SDL 库中用于管理图像和视频的模块。它提供了一系列函数和数据结构，用于创建、管理和操作窗口、渲染器、[[OpenGL]] 上下文等与图像和视频相关的资源。

SDL_video 模块包含了许多与图像和视频处理相关的函数，例如创建窗口、创建渲染器、设置窗口属性、处理事件等。它也提供了一些与 [[OpenGL]] 相关的函数，用于创建和管理 [[OpenGL]] 渲染上下文。

以下是 SDL_video 模块中一些常用函数和数据结构：

- [[SDL_CreateWindow()]]：创建一个窗口。
- `SDL_CreateRenderer()`：创建一个渲染器。
- [[SDL_GL_CreateContext()]]：创建一个 [[OpenGL]] 渲染上下文。
- `SDL_GetWindowSurface()`：获取窗口的表面。
- `SDL_GetRendererInfo()`：获取渲染器的信息。
- `SDL_SetWindowFullscreen()`：设置窗口的全屏模式。
- `SDL_PollEvent()`：检查是否有事件发生。
- [[SDL_Window]] : SDL 中表示窗口的数据结构。

SDL_video 模块提供了丰富的功能，能够满足图像和视频处理的需求，并与其他 SDL 模块协同工作，使得开发者可以方便地创建和管理图像和视频相关的应用程序。