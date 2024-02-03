
----
`SDL_WarpMouseInWindow` 是一个 SDL 函数，用于将鼠标光标移动到指定窗口的指定位置。
### 函数原型
```c
int SDL_WarpMouseInWindow(SDL_Window* window, int x, int y);
```
### 参数
- `window`：要将鼠标光标移动到其中的窗口。
- `x`：鼠标光标要移动到的目标位置的 x 坐标。
- `y`：鼠标光标要移动到的目标位置的 y 坐标。
### 返回值
- 如果成功移动了鼠标光标，则返回零；如果出现错误，则返回非零值。
### 示例用法
```c
// 将鼠标光标移动到窗口左上角
SDL_WarpMouseInWindow(window, 0, 0);
```
在这个示例中，`SDL_WarpMouseInWindow` 函数被用来将鼠标光标移动到指定窗口的左上角。