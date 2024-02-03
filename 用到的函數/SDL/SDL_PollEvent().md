
----
`SDL_PollEvent` 是一个 SDL 函数，用于检查事件队列中是否有待处理的事件，并将事件存储在提供的 `SDL_Event` 结构中。

### 函数原型
```c
int SDL_PollEvent(SDL_Event* event);
```

### 参数
- `event`：一个指向 `SDL_Event` 结构的指针，用于存储检测到的事件。

### 返回值
- 如果有待处理的事件，则返回非零值；如果事件队列为空，则返回零。

### 示例用法
```c
SDL_Event event;
while (SDL_PollEvent(&event)) {
    switch (event.type) {
        case SDL_QUIT:
            // 处理窗口关闭事件
            break;
        case SDL_KEYDOWN:
            // 处理键盘按下事件
            break;
        case SDL_MOUSEBUTTONDOWN:
            // 处理鼠标按下事件
            break;
        // 其他事件处理...
    }
}
```

在这个示例中，`SDL_PollEvent` 函数用于检查事件队列中是否有待处理的事件，如果有，则将事件存储在 `SDL_Event` 结构中。然后，通过 `switch` 语句根据事件类型执行相应的操作。