  
---
`Mix_Init()` 是 [[SDL_mixer]] 库中用于初始化音频混合器的函数。它是使用 [[SDL_mixer]] 库时的第一个调用，必须在使用 [[SDL_mixer]] 的其他功能之前调用。

具体而言，`Mix_Init()` 负责初始化 [[SDL_mixer]] 库以准备加载和播放音频文件。通过调用这个函数，你可以启动 [[SDL_mixer]] 库并准备使用它的功能来加载音频文件并在应用程序中进行播放和混合。

这个函数的原型如下：

```cpp
int Mix_Init(int flags);
```
参数 `flags` 是一个位掩码，用于指定要初始化的音频混合器功能。常见的音频混合器功能包括：
- `MIX_INIT_FLAC`：初始化 FLAC 格式的音频处理功能。
- `MIX_INIT_MOD`：初始化 MOD 格式的音频处理功能。
- [[MIX_INIT_MP3]]：初始化 MP3 格式的音频处理功能。
- `MIX_INIT_OGG`：初始化 OGG 格式的音频处理功能。
示例用法：
```cpp
#include <SDL2/SDL.h>
#include <SDL2/SDL_mixer.h>
int main(int argc, char* argv[]) {
    // 初始化 SDL 库的视频子系统
    if (SDL_Init(SDL_INIT_VIDEO) < 0) {
        // 初始化失败，处理错误
        return -1;
    }
    // 初始化 SDL_mixer 库的音频混合器功能（例如 MP3 和 OGG 格式）
    int mixFlags = MIX_INIT_MP3 | MIX_INIT_OGG;
    if (!(Mix_Init(mixFlags) & mixFlags)) {
        // 初始化失败，处理错误
        SDL_Quit(); // 退出 SDL 库
        return -1;
    }
    // 其他初始化操作...
    // 加载和播放音频等操作...
    // 退出 SDL_mixer 库
    Mix_Quit();
    // 退出 SDL 库
    SDL_Quit();
    return 0;
}
```
在这个示例中，`Mix_Init(MIX_INIT_MP3 | MIX_INIT_OGG)` 用于初始化 [[SDL_mixer]] 库的音频混合器功能，然后进行其他初始化操作。如果初始化失败，程序将返回 -1。最后，调用 `Mix_Quit()` 函数退出 [[SDL_mixer]] 库。