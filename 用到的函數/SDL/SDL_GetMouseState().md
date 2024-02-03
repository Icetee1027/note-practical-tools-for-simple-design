
----
`SDL_GetMouseState` 是一个 SDL 函数，用于获取当前鼠标的位置和按钮状态。它返回当前鼠标的位置，并可以获取特定鼠标按钮的状态。

### 函数原型
```c
Uint32 SDL_GetMouseState(int* x, int* y);
```

### 参数
- `x`：一个指向整数的指针，用于存储当前鼠标的 X 坐标。
- `y`：一个指向整数的指针，用于存储当前鼠标的 Y 坐标。

### 返回值
- 返回一个 `Uint32` 类型的值，表示当前鼠标按钮的状态。如果某个按钮被按下，则相应的位会被设置为 1，否则为 0。

### 示例用法
```c
int mouse_x, mouse_y;
Uint32 mouse_state = SDL_GetMouseState(&mouse_x, &mouse_y);
if (mouse_state & SDL_BUTTON(SDL_BUTTON_LEFT)) {
    // 如果鼠标左键被按下
    // 执行某些操作
}
```

在这个示例中，`SDL_GetMouseState` 函数用于获取当前鼠标的位置和按钮状态，然后通过检查返回的状态来判断左键是否被按下，并执行相应的操作。