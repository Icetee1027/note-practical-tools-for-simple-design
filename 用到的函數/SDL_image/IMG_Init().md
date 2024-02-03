  
----
`IMG_Init()` 是 [[SDL_image]] 库中用于初始化图像处理功能的函数。它是使用 [[SDL_image]] 库时的第一个调用，必须在使用 [[SDL_image]] 的其他功能之前调用。

具体而言，`IMG_Init()` 负责初始化 [[SDL_image]] 库以准备加载和处理图像文件，例如 PNG、JPG、TIF 等格式的图像文件。通过调用这个函数，你可以启动 [[SDL_image]] 库并准备使用它的功能来加载图像并在应用程序中进行渲染或处理。

这个函数的原型如下：
```cpp
int IMG_Init(int flags);
```
参数 `flags` 是一个位掩码，用于指定要初始化的图像处理功能。常见的图像处理功能包括：
- [[IMG_INIT_JPG]]：初始化 JPG 格式的图像处理功能。
- [[IMG_INIT_PNG]]：初始化 PNG 格式的图像处理功能。
- `IMG_INIT_TIF`：初始化 TIF 格式的图像处理功能。
- `IMG_INIT_WEBP`：初始化 WEBP 格式的图像处理功能。
- `IMG_INIT_JXL`：初始化 JXL 格式的图像处理功能。
- `IMG_INIT_AVIF`：初始化 AVIF 格式的图像处理功能。

示例用法：
```cpp
#include <SDL2/SDL.h>
#include <SDL2/SDL_image.h>
int main(int argc, char* argv[]) {
    // 初始化 SDL 库的视频子系统
    if (SDL_Init(SDL_INIT_VIDEO) < 0) {
        // 初始化失败，处理错误
        return -1;
    }
    // 初始化 SDL_image 库的图像处理功能（例如 JPG 和 PNG 格式）
    int imgFlags = IMG_INIT_JPG | IMG_INIT_PNG;
    if (!(IMG_Init(imgFlags) & imgFlags)) {
        // 初始化失败，处理错误
        SDL_Quit(); // 退出 SDL 库
        return -1;
    }
    // 其他初始化操作...
    // 加载和渲染图像等操作...
    // 退出 SDL_image 库
    IMG_Quit();
    // 退出 SDL 库
    SDL_Quit();
    return 0;
}
```
在这个示例中，`IMG_Init(IMG_INIT_JPG | IMG_INIT_PNG)` 用于初始化 [[SDL_image]] 库的图像处理功能，然后进行其他初始化操作。如果初始化失败，程序将返回 -1。最后，调用 `IMG_Quit()` 函数退出 [[SDL_image]] 库。