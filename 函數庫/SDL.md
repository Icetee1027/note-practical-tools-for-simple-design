[SDL2/Libraries - SDL Wiki (libsdl.org)](https://wiki.libsdl.org/SDL2/Libraries)

---
SDL 是一个跨平台的多媒体库，提供了对图形、音频、输入设备等多种多媒体功能的支持，适用于游戏开发、多媒体应用程序等领域。通过 SDL 库，开发者可以在不同的操作系统上编写相同的代码，并实现跨平台的多媒体应用程序。

在 `SDL.c` 文件中，可能包含了使用 SDL 库的初始化、创建窗口、处理事件、渲染图形等功能的代码示例。这个文件可以作为入门学习 SDL 库的参考，开发者可以从中了解 SDL 库的基本用法和功能，以便开始开发自己的多媒体应用程序。
通常，`SDL` 包含以下内容：
- 引入 SDL 头文件和必要的库文件。
- SDL 库的初始化和关闭代码。
- 创建窗口和渲染器的代码。
- 处理事件循环的代码。
- 渲染图形和处理音频的代码。
- 释放资源和关闭 SDL 库的代码。

为了更好地理解和使用 SDL 库，建议参考 SDL 官方文档和示例代码。

---
以下是一些常用的 SDL 函数，它们用于处理窗口、图像、渲染、事件等方面：
1. **初始化和关闭：**
   - [[SDL_Init()]]：初始化 SDL 库。
   - [[SDL_Quit()]]：关闭 SDL 库。
2. **创建和管理窗口：**
   - [[SDL_CreateWindow()]]：创建窗口。
   - [[SDL_DestroyWindow()]]：销毁窗口。
   - `SDL_GetWindowSurface()`：获取窗口表面。
   - `SDL_SetWindowTitle()`：设置窗口标题。
3. **图像加载和处理：**
   - `SDL_LoadBMP()`：加载 BMP 图像。
   - `SDL_FreeSurface()`：释放表面内存。
   - `SDL_ConvertSurface()`：转换表面格式。
4. **渲染器和渲染：**
   - `SDL_CreateRenderer()`：创建渲染器。
   - `SDL_DestroyRenderer()`：销毁渲染器。
   - `SDL_SetRenderDrawColor()`：设置渲染器绘制颜色。
   - `SDL_RenderClear()`：清空渲染目标。
   - `SDL_RenderCopy()`：复制纹理到渲染目标。
   - `SDL_RenderPresent()`：更新渲染目标显示。
5. **事件处理：**
   - `SDL_PollEvent()`：获取事件。
   - `SDL_PumpEvents()`：更新事件状态。
   - `SDL_WaitEvent()`：等待事件。
6. **定时器：**
   - `SDL_GetTicks()`：获取毫秒级别的系统时间。
7. **键盘和鼠标输入：**
   - `SDL_GetKeyboardState()`：获取键盘状态。
   - `SDL_GetMouseState()`：获取鼠标状态。
8. **音频：**
   - `SDL_OpenAudio()`：打开音频设备。
   - `SDL_LoadWAV()`：加载 WAV 格式音频文件。
   - `SDL_PauseAudio()`：暂停或继续音频回放。
9. **其他功能：**
   - `SDL_GetError()`：获取错误信息。
   - `SDL_Delay()`：延迟执行。
这些函数覆盖了 SDL 库的各个方面，开发者可以根据自己的需求选择适合的函数来实现相应的功能。使用这些函数可以轻松地创建基于 SDL 的多媒体应用程序，如游戏、多媒体播放器等。