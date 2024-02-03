
----
`GL_DEBUG_OUTPUT` 是 [[OpenGL]] 中的一个调试输出功能。它是一个 [[OpenGL]] 调试扩展的一部分，允许应用程序在 [[OpenGL]] 发生错误或警告时接收调试消息。

当启用了 `GL_DEBUG_OUTPUT` 功能后，[[OpenGL]] 将会在发生错误或警告时生成调试消息，并通过注册的调试回调函数来传递这些消息给应用程序。开发者可以利用这些调试消息来调试和优化 [[OpenGL]] 应用程序。

在使用 `GL_DEBUG_OUTPUT` 功能时，通常需要进行以下步骤：

1. 启用调试输出功能：通过调用 `glEnable()` 函数并传入 `GL_DEBUG_OUTPUT` 参数来启用调试输出功能。

   ```c
   glEnable(GL_DEBUG_OUTPUT);
   ```

2. 设置调试回调函数：通过调用 `glDebugMessageCallback()` 函数来设置调试消息的回调函数，以接收 [[OpenGL]] 发出的调试消息。

   ```c
   void debugCallback(GLenum source, GLenum type, GLuint id, GLenum severity,
                      GLsizei length, const GLchar *message, const void *userParam);

   glDebugMessageCallback(debugCallback, nullptr);
   ```

3. 确保调试输出已启用：可以通过查询 [[OpenGL]] 环境的调试输出状态来确保调试输出功能已经启用。

   ```c
   GLint isDebugEnabled = 0;
   glGetIntegerv(GL_CONTEXT_FLAGS, &isDebugEnabled);

   if (isDebugEnabled & GL_CONTEXT_FLAG_DEBUG_BIT) {
       // 调试输出功能已启用
   }
   ```

通过以上步骤，应用程序就可以接收并处理 [[OpenGL]] 发出的调试消息，以便更好地调试和优化 [[OpenGL]] 应用程序。