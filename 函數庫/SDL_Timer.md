
----
SDL_timer 是 [[SDL]] 库中负责处理时间相关功能的模块。它提供了以下主要功能：

1. **获取时间：**
   - `SDL_GetTicks()`：返回自 [[SDL]] 库初始化以来经过的毫秒数，用于计算程序运行时间或实现简单的延迟。
   - `SDL_GetPerformanceCounter()`：返回高精度的性能计数器的值，通常用于实现精确的时间间隔和帧率控制。

2. **性能计数器：**
   - `SDL_GetPerformanceFrequency()`：返回性能计数器的频率，用于将性能计数器的值转换为秒。

3. **延迟执行：**
   - `SDL_Delay()`：让程序延迟指定的毫秒数，用于实现简单的延迟效果。

SDL_timer 模块提供了对时间的基本操作，以及获取高精度时间的能力，使开发者能够实现精确的时间控制和延迟执行。这些功能在游戏开发中经常用于实现游戏循环中的时间管理、动画效果、延迟执行等功能。