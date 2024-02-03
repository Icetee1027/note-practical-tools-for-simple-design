

----
`SDL_GL_CreateContext()` 是 SDL 中用于创建 [[OpenGL]] 渲染上下文的函数。[[OpenGL]] 渲染上下文是一个管理 [[OpenGL]] 状态信息的对象，它包含了所有 [[OpenGL]] 状态的当前值。

在使用 SDL 进行 [[OpenGL]] 图形渲染时，需要先创建一个 [[OpenGL]] 渲染上下文，然后才能进行 [[OpenGL]] 相关的操作。`SDL_GL_CreateContext()` 函数就是用来创建这个 [[OpenGL]] 渲染上下文的。

函数原型如下所示：
```c
SDL_GLContext SDL_GL_CreateContext(SDL_Window* window);
```

其中，`window` 参数是一个指向 SDL 窗口的指针，表示要将 [[OpenGL]] 渲染上下文与哪个窗口关联起来。函数返回一个 `SDL_GLContext` 类型的指针，表示创建的 [[OpenGL]] 渲染上下文。

创建成功后，可以使用返回的 `SDL_GLContext` 指针来进行 [[OpenGL]] 相关的操作，如绘制图形、设置状态等。需要注意的是，每个 SDL 窗口只能关联一个 [[OpenGL]] 渲染上下文。

通常情况下，需要在程序初始化时调用 `SDL_GL_CreateContext()` 函数来创建 [[OpenGL]] 渲染上下文，并在程序退出时调用 `SDL_GL_DeleteContext()` 函数来释放相应的资源。
