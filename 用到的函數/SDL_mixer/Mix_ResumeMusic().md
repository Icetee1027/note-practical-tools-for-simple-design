
----
`Mix_ResumeMusic()` 是 [[SDL_mixer]] 库中用于恢复暂停的音乐的函数之一。调用此函数将继续播放当前暂停的音乐，从暂停的位置开始继续播放。
### 函数原型
```cpp
void Mix_ResumeMusic();
```
### 返回值
- 无。
### 注意事项
- 调用 `Mix_ResumeMusic()` 函数将继续播放当前暂停的音乐，从暂停的位置开始继续播放。
- 如果当前没有暂停的音乐，调用此函数将不会产生任何效果。
- 若要暂停当前正在播放的音乐，可以使用 `Mix_PauseMusic()` 函数。
### 示例用法
```cpp
Mix_ResumeMusic();
```
以上示例代码演示了如何使用 `Mix_ResumeMusic()` 函数恢复暂停的音乐。