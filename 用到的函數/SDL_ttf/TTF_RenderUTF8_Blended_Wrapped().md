
----
`TTF_RenderUTF8_Blended_Wrapped` 是 SDL_ttf 库中用于生成包含指定 UTF-8 格式文本的表面（surface）的函数。生成的表面包含了根据指定字体和颜色渲染的文本，并且支持自动换行。
### 函数原型

```c
SDL_Surface* TTF_RenderUTF8_Blended_Wrapped(TTF_Font* font, const char* text, SDL_Color color, Uint32 wrapLength);
```
### 参数

- `font`：要用于渲染文本的字体对象，是一个指向 `TTF_Font` 结构体的指针。
- `text`：要渲染的 UTF-8 格式的文本字符串。
- `color`：文本的颜色，是一个 `SDL_Color` 结构体，表示为 `{Uint8 r, Uint8 g, Uint8 b, Uint8 a}`。
- `wrapLength`：自动换行的宽度（以像素为单位）。当文本的宽度超过 `wrapLength` 时，将自动换行。

### 返回值

- 如果成功生成了表面，则返回一个指向 `SDL_Surface` 结构体的指针，该表面包含了渲染后的文本。
- 如果生成表面失败，则返回 `NULL`。

### 注意事项

- 要使用本函数，必须先调用 `TTF_Init()` 来初始化 SDL_ttf 库。
- 生成的表面包含了渲染后的文本，可以使用 SDL 库中的其他函数将其绘制到窗口上。

### 示例用法

```c
#include <SDL_ttf.h>

// 初始化 SDL_ttf 库
if (TTF_Init() == -1) {
    // 处理初始化失败的情况
}

// 加载字体文件
TTF_Font* font = TTF_OpenFont("arial.ttf", 24);
if (font == NULL) {
    // 处理字体加载失败的情况
}

// 设置文本颜色
SDL_Color textColor = {255, 255, 255, 255}; // 白色

// 渲染文本并生成表面，设置自动换行宽度为 400 像素
SDL_Surface* textSurface = TTF_RenderUTF8_Blended_Wrapped(font, "Hello, SDL!", textColor, 400);
if (textSurface == NULL) {
    // 处理表面生成失败的情况
}

// 绘制文本表面到屏幕上

// 释放字体对象
TTF_CloseFont(font);

// 释放文本表面
SDL_FreeSurface(textSurface);

// 退出 SDL_ttf 库
TTF_Quit();
```

以上示例演示了如何使用 `TTF_RenderUTF8_Blended_Wrapped` 函数渲染包含指定 UTF-8 格式文本的表面，并设置自动换行宽度。