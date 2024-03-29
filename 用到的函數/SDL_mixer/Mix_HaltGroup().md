
---
`Mix_HaltGroup()` 函数是 [[SDL_mixer]] 库中用于停止指定音频通道组中所有音频的播放的函数。

通常，[[SDL_mixer]] 库允许将音频通道划分为不同的组，以便对音频进行更精细的控制。`Mix_HaltGroup()` 函数允许开发者停止指定组中所有正在播放的音频，以便在某些情况下进行集中控制或管理。

以下是 `Mix_HaltGroup()` 函数的原型：

```c
int Mix_HaltGroup(int tag)
```

参数 `tag` 是指定的音频组标签，用于标识要停止的音频组。如果成功停止了至少一个音频，则返回值为大于等于 0 的值；如果没有任何音频被停止，则返回值为 -1。

需要注意的是，调用 `Mix_HaltGroup()` 函数后，指定组中所有正在播放的音频将被停止，包括循环播放的音频。