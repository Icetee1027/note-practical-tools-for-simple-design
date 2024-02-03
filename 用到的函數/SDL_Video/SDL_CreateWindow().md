  
---
`SDL_CreateWindow()` 是 SDL 库中用于创建窗口的函数。它用于创建一个可视的窗口，用于图形界面的显示。

具体而言，`SDL_CreateWindow()` 函数创建一个具有指定属性的窗口，并返回一个指向新窗口的指针。你可以在创建窗口时指定窗口的标题、位置、大小以及其他属性。一旦窗口创建成功，你就可以在这个窗口中渲染图形、处理事件等操作。

这个函数的原型如下：

```cpp
SDL_Window* SDL_CreateWindow(const char* title, int x, int y, int w, int h, Uint32 flags);
```

参数说明：
- `title`：窗口的标题。
- `x` 和 `y`：窗口的左上角在屏幕上的坐标位置。
- `w` 和 `h`：窗口的宽度和高度。
- `flags`：窗口的属性标志，可以是以下值的组合：
- `SDL_WINDOW_FULLSCREEN`：全屏窗口。
- [[SDL_WINDOW_OPENGL]]：窗口使用 [[OpenGL]] 渲染。
- `SDL_WINDOW_RESIZABLE`：窗口可以被用户调整大小。
- `SDL_WINDOW_BORDERLESS`：窗口没有边框。
- `SDL_WINDOW_SHOWN`：窗口可见。
- `SDL_WINDOW_HIDDEN`：窗口隐藏。
- `SDL_WINDOW_INPUT_GRABBED`：窗口捕获输入焦点。
- `SDL_WINDOW_INPUT_FOCUS`：窗口有输入焦点。
- `SDL_WINDOW_MOUSE_FOCUS`：窗口有鼠标焦点。
- `SDL_WINDOW_ALLOW_HIGHDPI`：窗口支持高 DPI 显示。
示例用法：
```cpp
#include <SDL2/SDL.h>
int main(int argc, char* argv[]) {
    // 初始化 SDL 库
    if (SDL_Init(SDL_INIT_VIDEO) < 0) {
        // 初始化失败，处理错误
        return -1;
    }
    // 创建一个窗口
    SDL_Window* window = SDL_CreateWindow("My Window", SDL_WINDOWPOS_CENTERED, SDL_WINDOWPOS_CENTERED, 800, 600, SDL_WINDOW_SHOWN);
    if (window == nullptr) {
        // 窗口创建失败，处理错误
        SDL_Quit(); // 退出 SDL 库
        return -1;
    }
    // 其他初始化操作...
    // 进行图形渲染、事件处理等操作...
    // 销毁窗口
    SDL_DestroyWindow(window);
    // 退出 SDL 库
    SDL_Quit();
    return 0;
}
```
在这个示例中，`SDL_CreateWindow()` 用于创建一个标题为 "My Window"、大小为 800x600 的窗口，并将窗口放置在屏幕中央。如果窗口创建失败，程序将返回 -1。最后，通过调用 [[SDL_DestroyWindow()]] 销毁窗口，然后调用 `SDL_Quit()` 退出 SDL 库。

默认情况下，`SDL_CreateWindow()` 函数的参数值如下：
- `title`：窗口标题，默认为空字符串。
- `x`：窗口的初始 x 坐标，默认为 `SDL_WINDOWPOS_UNDEFINED`，表示窗口的 x 坐标将由系统决定。
- `y`：窗口的初始 y 坐标，默认为 `SDL_WINDOWPOS_UNDEFINED`，表示窗口的 y 坐标将由系统决定。
- `w`：窗口的宽度，默认为 `640`。
- `h`：窗口的高度，默认为 `480`。
- `flags`：窗口的标志，默认为 `0`，表示创建一个普通的可见窗口。