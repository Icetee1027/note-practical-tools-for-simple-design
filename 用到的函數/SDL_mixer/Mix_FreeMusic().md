
----
`Mix_FreeMusic()` 是 SDL_mixer 库中的一个函数，用于释放之前加载的音乐资源，释放内存并清理相关资源，以防止内存泄漏。

### 函数签名
```cpp
void Mix_FreeMusic(Mix_Music *music)
```
### 参数
- `music`：要释放的音乐资源的指针，类型为 `Mix_Music*`。
### 返回值
- 无
### 功能
该函数用于释放之前使用 `Mix_LoadMUS()` 或 `Mix_LoadMUSType_RW()` 加载的音乐资源。调用该函数后，音乐资源所占用的内存将被释放，相关资源也将被清理，从而避免内存泄漏。
### 示例用法
```cpp
Mix_Music *music = Mix_LoadMUS("music.wav");
// 使用音乐...
Mix_FreeMusic(music); // 释放音乐资源
```

### 注意事项
- 在释放音乐资源之前，应确保音乐资源已经加载成功。
- 每次加载音乐资源后都应该相应地调用 `Mix_FreeMusic()` 来释放资源，以防止内存泄漏。