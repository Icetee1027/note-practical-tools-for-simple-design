
---
`glewInit()` 是 [[GLEW]]（OpenGL Extension Wrangler Library）中用于初始化 [[OpenGL]] 扩展加载器的函数。它必须在创建 [[OpenGL]] 上下文之后，但在使用任何 [[OpenGL]] 扩展之前调用。

具体而言，`glewInit()` 负责初始化 [[GLEW]] 库以准备加载和管理 [[OpenGL]] 扩展。[[OpenGL]] 扩展提供了 [[OpenGL]] 标准之外的功能，例如高级渲染技术、硬件特定的功能等。通过调用这个函数，你可以启动 [[GLEW]] 库并准备使用它的功能来加载和管理 [[OpenGL]] 扩展。

这个函数的原型如下：
```cpp
GLenum glewInit();
```
返回值为 `GLenum` 类型，表示初始化的状态。如果返回值为 `GLEW_OK`，表示初始化成功；如果返回值不是 `GLEW_OK`，表示初始化失败，你应该进一步处理错误。

示例用法：
```cpp
#include <GL/glew.h>
#include <SDL2/SDL.h>
#include <SDL2/SDL_opengl.h>
int main(int argc, char* argv[]) {
    // 初始化 SDL 库
    if (SDL_Init(SDL_INIT_VIDEO) < 0) {
        // 初始化失败，处理错误
        return -1;
    }
    // 创建一个 OpenGL 窗口
    SDL_Window* window = SDL_CreateWindow("OpenGL Window", SDL_WINDOWPOS_CENTERED, SDL_WINDOWPOS_CENTERED, 800, 600, SDL_WINDOW_OPENGL);
    if (window == nullptr) {
        // 窗口创建失败，处理错误
        SDL_Quit(); // 退出 SDL 库
        return -1;
    }
    // 创建 OpenGL 上下文
    SDL_GLContext context = SDL_GL_CreateContext(window);
    if (context == nullptr) {
        // 上下文创建失败，处理错误
        SDL_DestroyWindow(window);
        SDL_Quit(); // 退出 SDL 库
        return -1;
    }
    // 初始化 GLEW 库
    GLenum status = glewInit();
    if (status != GLEW_OK) {
        // GLEW 初始化失败，处理错误
        SDL_GL_DeleteContext(context);
        SDL_DestroyWindow(window);
        SDL_Quit(); // 退出 SDL 库
        return -1;
    }
    // 进行 OpenGL 渲染等操作...
    // 销毁 OpenGL 上下文
    SDL_GL_DeleteContext(context);
    // 销毁窗口
    SDL_DestroyWindow(window);
    // 退出 SDL 库
    SDL_Quit();
    return 0;
}
```
在这个示例中，`glewInit()` 用于初始化 [[GLEW]] 库，然后创建了一个支持 [[OpenGL]] 渲染的窗口，并在窗口上创建了一个 [[OpenGL]] 上下文。如果初始化失败，程序将返回 -1。最后，调用 `SDL_GL_DeleteContext()` 销毁了 [[OpenGL]] 上下文，并调用 [[SDL_DestroyWindow()]] 销毁了窗口。