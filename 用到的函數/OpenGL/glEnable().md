
---

`glEnable()` 是 [[OpenGL]] 中用于启用特定的 [[OpenGL]] 功能的函数。它用于启用 [[OpenGL]] 的各种功能，例如深度测试、剪裁测试、光照等。

具体而言，`glEnable()` 函数接受一个参数，表示要启用的 [[OpenGL]] 功能的标识符。通过调用这个函数，你可以在渲染时启用各种 [[OpenGL]] 功能，以实现所需的图形效果。

这个函数的原型如下：
```cpp
void glEnable(GLenum cap);
```
参数 `cap` 是一个枚举值，表示要启用的 [[OpenGL]] 功能。常见的功能包括：

- [[GL_BLEND]]：启用颜色混合，用于实现半透明效果。
- `GL_TEXTURE_2D`：启用纹理映射，用于在图形上贴纹理。
- `GL_CULL_FACE`：启用面剔除，用于剔除不可见的面。
- `GL_LIGHTING`：启用光照计算，用于进行光照模拟。
- [[GL_DEBUG_OUTPUT]] :启用 [[OpenGL]] 发生错误或警告时接收调试消息
- [[GL_DEPTH_TEST]]: 启用深度测试
- `GL_CULL_FACE`: 启用背面剔除
- `GL_COLOR_LOGIC_OP`: 启用颜色逻辑运算
- `GL_DITHER`: 启用抖动
- `GL_SCISSOR_TEST`: 启用剪裁测试
- `GL_POLYGON_SMOOTH`: 启用多边形平滑
- `GL_MULTISAMPLE`: 启用多重采样
- `GL_POLYGON_OFFSET_FILL`: 启用多边形偏移
- `GL_TEXTURE_WRAP_S`: 启用纹理缠绕 (S 方向)
- `GL_TEXTURE_WRAP_T`: 启用纹理缠绕 (T 方向)
- `GL_TEXTURE_MIN_FILTER`: 启用纹理过滤 (缩小)
- `GL_TEXTURE_MAG_FILTER`: 启用纹理过滤 (放大)
- [[GL_DEBUG_OUTPUT_SYNCHRONOUS]] : 用于指定调试输出的同步模式。
}
```
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
    // 启用深度测试
    glEnable(GL_DEPTH_TEST);
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
在这个示例中，`glEnable(GL_DEPTH_TEST)` 用于启用深度测试功能。然后创建了一个支持 [[OpenGL]] 渲染的窗口，并在窗口上创建了一个 [[OpenGL]] 上下文。最后，通过调用 `SDL_GL_DeleteContext()` 销毁了 [[OpenGL]] 上下文，并调用 [[SDL_DestroyWindow()]] 销毁了窗口。