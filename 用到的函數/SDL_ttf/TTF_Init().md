
---
`TTF_Init()` 是 [[SDL_ttf]] 库中用于初始化 TrueType 字体支持的函数。它是使用 [[SDL_ttf]] 库时的第一个调用，必须在使用 [[SDL_ttf]] 的其他功能之前调用。

具体而言，`TTF_Init()` 负责初始化 [[SDL_ttf]] 库以准备加载和渲染 TrueType 字体。通过调用这个函数，你可以启动 [[SDL_ttf]] 库并准备使用它的功能来加载 TrueType 字体文件并在应用程序中进行文本渲染。

这个函数没有参数，它的返回值为整数，表示初始化成功的标志位。如果返回值为 0，表示初始化失败；如果返回值为非零值，表示初始化成功，并返回成功初始化的标志位。

示例用法：
```cpp
#include <SDL2/SDL.h>
#include <SDL2/SDL_ttf.h>
int main(int argc, char* argv[]) {
    // 初始化 SDL 库的视频子系统
    if (SDL_Init(SDL_INIT_VIDEO) < 0) {
        // 初始化失败，处理错误
        return -1;
    }
    // 初始化 SDL_ttf 库
    if (TTF_Init() < 0) {
        // 初始化失败，处理错误
        SDL_Quit(); // 退出 SDL 库
        return -1;
    }
    // 其他初始化操作...
    // 加载和渲染 TrueType 字体等操作...
    // 退出 SDL_ttf 库
    TTF_Quit();
    // 退出 SDL 库
    SDL_Quit();
    return 0;
}
```
在这个示例中，`TTF_Init()` 用于初始化 [[SDL_ttf]] 库，然后进行其他初始化操作。如果初始化失败，程序将返回 -1。最后，调用 `TTF_Quit()` 函数退出 [[SDL_ttf]] 库。