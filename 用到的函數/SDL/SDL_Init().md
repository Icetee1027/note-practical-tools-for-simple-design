  
---
`SDL_Init()` 是 [[SDL]]（Simple DirectMedia Layer）库中用于初始化库的函数。它是使用 SDL 库时的第一个调用，必须在使用 SDL 的其他功能之前调用。

具体而言，`SDL_Init()` 负责初始化 SDL 库的各种子系统，包括视频、音频、事件处理、定时器等。通过调用这个函数，你可以启动 SDL 库并准备使用它的功能来创建图形应用程序、游戏等。

这个函数的原型如下：
```cpp
int SDL_Init(Uint32 flags);
```

参数 `flags` 是一个位掩码，用于指定要初始化的子系统。常见的子系统包括：
- [[SDL_INIT_VIDEO]]：初始化视频子系统，用于图形显示。
- `SDL_INIT_AUDIO`：初始化音频子系统，用于声音播放。
- `SDL_INIT_EVENTS`：初始化事件子系统，用于处理事件。
- `SDL_INIT_TIMER`：初始化定时器子系统，用于处理时间。
- `SDL_INIT_JOYSTICK`：初始化游戏手柄子系统，用于处理游戏手柄。
- `SDL_INIT_GAMECONTROLLER`：初始化游戏控制器子系统，用于处理游戏控制器。
- `SDL_INIT_HAPTIC`：初始化触觉反馈子系统，用于处理力反馈。
- `SDL_INIT_SENSOR`：初始化传感器子系统，用于处理传感器数据。
- `SDL_INIT_EVERYTHING`：初始化所有可用的子系统。
  
示例用法：
```cpp
#include <SDL2/SDL.h>
int main(int argc, char* argv[]) {
    // 初始化 SDL 库的视频子系统
    if (SDL_Init(SDL_INIT_VIDEO) < 0) {
        // 初始化失败，处理错误
        return -1;
    }
    // 其他初始化操作...
    // 退出 SDL 库
    SDL_Quit();
    return 0;
}
```
在这个示例中，`SDL_Init(SDL_INIT_VIDEO)` 用于初始化 SDL 库的视频子系统，然后进行其他初始化操作。如果初始化失败，程序将返回 -1。最后，调用 `SDL_Quit()` 函数退出 SDL 库。

