----
`SDL_GL_DeleteContext()` 是 SDL 函式庫中的一個函式，用於釋放由 `SDL_GL_CreateContext()` 創建的 [[OpenGL]] 上下文。

在使用 SDL 創建了一個支持 [[OpenGL]] 渲染的窗口後，你可以使用 `SDL_GL_CreateContext()` 函式來創建一個與窗口關聯的 [[OpenGL]] 上下文。當你不再需要這個 [[OpenGL]] 上下文時（比如當你關閉了窗口或應用程式退出時），你應該使用 `SDL_GL_DeleteContext()` 函式來釋放這個上下文，以防止資源泄漏和記憶體洩漏。

通常情況下，你應該在應用程式退出前（比如在窗口被銷毀時）調用 `SDL_GL_DeleteContext()` 函式，以確保釋放所有的 [[OpenGL]] 相關資源。

調用 `SDL_GL_DeleteContext()` 函式後，相應的 [[OpenGL]] 上下文將被釋放，並且與窗口解除關聯。