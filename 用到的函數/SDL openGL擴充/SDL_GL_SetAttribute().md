  
---

`SDL_GL_SetAttribute()` 是 SDL 库中用于设置 [[OpenGL]] 窗口属性的函数。它用于配置创建的窗口以支持 [[OpenGL]] 渲染。
具体而言，`SDL_GL_SetAttribute()` 函数允许你设置与 [[OpenGL]] 相关的属性，例如 [[OpenGL]] 版本、缓冲区大小、双缓冲、深度缓冲等。通过设置这些属性，你可以控制创建的窗口如何与 [[OpenGL]] 交互和渲染图形。

这个函数的原型如下：

```cpp
int SDL_GL_SetAttribute(SDL_GLattr attr, int value);
```
参数说明：
- `attr`：要设置的 [[OpenGL]] 属性，是一个枚举值，例如 `SDL_GL_RED_SIZE`、`SDL_GL_DOUBLEBUFFER` 等。
- `value`：属性的值，具体取决于不同的属性。

> SDL_GL_SetAttribute([[SDL_GL_CONTEXT_PROFILE_MASK]],
 >                   [[SDL_GL_CONTEXT_PROFILE_CORE]]);
> SDL_GL_SetAttribute([[SDL_GL_CONTEXT_MAJOR_VERSION]], 4);
> SDL_GL_SetAttribute([[SDL_GL_CONTEXT_MINOR_VERSION]], 1);


示例用法：
```cpp
#include <SDL2/SDL.h>
int main(int argc, char* argv[]) {
    // 初始化 SDL 库
    if (SDL_Init(SDL_INIT_VIDEO) < 0) {
        // 初始化失败，处理错误
        return -1;
    }
    // 设置 OpenGL 版本为 3.3
    SDL_GL_SetAttribute(SDL_GL_CONTEXT_MAJOR_VERSION, 3);
    SDL_GL_SetAttribute(SDL_GL_CONTEXT_MINOR_VERSION, 3);
    // 设置双缓冲
    SDL_GL_SetAttribute(SDL_GL_DOUBLEBUFFER, 1);
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
    glewInit();
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
在这个示例中，通过调用 `SDL_GL_SetAttribute()` 设置了 [[OpenGL]] 版本为 3.3，并启用了双缓冲。然后创建了一个支持 [[OpenGL]] 渲染的窗口，并在窗口上创建了一个 [[OpenGL]] 上下文。最后，调用 `SDL_GL_DeleteContext()` 销毁了 [[OpenGL]] 上下文，并调用 [[SDL_DestroyWindow()]]销毁了窗口。