
----
`SDL_GetPerformanceCounter()` 是 [[SDL_Timer]] 库中的一个函数，用于获取高精度的性能计数器的当前值。这个函数通常用于测量时间间隔或者性能分析。

使用 `SDL_GetPerformanceCounter()` 函数获取的计数值通常是以一个特定的时间单位来表示的，例如毫秒或纳秒，这取决于系统的配置。通过比较不同时间点获取的计数值，可以计算出时间间隔，进而进行性能分析或者实现游戏逻辑中的时间相关功能。
一般情况下，使用这个函数的一般步骤如下：
1. 在需要开始计时的地方调用 `SDL_GetPerformanceCounter()` 获取起始计数值。
2. 在需要结束计时的地方再次调用 `SDL_GetPerformanceCounter()` 获取结束计数值。
3. 使用结束计数值减去起始计数值，得到时间间隔。
4. 如果需要，将时间间隔转换成适合的时间单位。

以下是一个简单的示例代码：

```c
Uint64 startTime = SDL_GetPerformanceCounter();

// 执行需要计时的操作

Uint64 endTime = SDL_GetPerformanceCounter();

double elapsedTime = (double)(endTime - startTime) / SDL_GetPerformanceFrequency();
```

在这个示例中，`SDL_GetPerformanceFrequency()` 函数用于获取性能计数器的频率，这个频率表示每秒钟性能计数器的计数次数。通过将时间间隔除以频率，就可以得到以秒为单位的时间间隔。